# 🛒 GALLERIA · SHOPPING LIST

갤러리아 백화점의 블랙&골드 프리미엄 톤과 쿠팡의 강렬한 레드 액션 컬러를 결합한 쇼핑 리스트 웹 앱입니다. 별도의 빌드 과정이나 프레임워크 없이 단일 HTML 파일로 동작하며, 데이터는 **Supabase(Postgres) 데이터베이스**에 저장되어 여러 기기/브라우저에서 실시간으로 동기화됩니다.

## 기능

- 물건 추가 (버튼 클릭 또는 Enter 키)
- 항목 체크/체크 해제 (구매 완료 표시)
- 항목 삭제
- 체크된 항목 일괄 삭제
- **Supabase `shopping_items` 테이블에 저장** — 로컬 저장이 아닌 클라우드 DB 동기화
- Supabase Realtime 구독으로 다른 탭/기기의 변경 사항도 즉시 반영
- 라이트/다크 모드 자동 대응 (`prefers-color-scheme`)

## 디자인 컨셉

- **헤더**: 갤러리아 백화점풍 블랙 바탕 + 골드(`#b8933f`) 세리프 브랜드 마크
- **액션 컬러**: 쿠팡풍 레드(`#e51937`) 버튼/체크 상태
- **본문 폰트**: Noto Sans KR, **브랜드 타이틀**: Playfair Display(세리프)

## 실행 방법

`index.html` 파일을 브라우저로 열면 바로 사용할 수 있습니다. (정적 파일이므로 로컬 서버 없이도 실행 가능하지만, 일부 브라우저의 `file://` 보안 정책 때문에 `python -m http.server` 등으로 띄우는 것을 권장합니다.)

```bash
# 예시
python -m http.server 8000
# http://localhost:8000 접속
```

## 백엔드 (Supabase)

- 테이블: `public.shopping_items (id uuid pk, text text, checked boolean, created_at timestamptz)`
- Row Level Security 활성화, 로그인 없는 개인용 데모 앱 특성상 `anon` 역할에 대해 select/insert/update/delete 전체 허용 정책 적용
- 클라이언트는 `@supabase/supabase-js` (CDN, jsDelivr)를 사용해 Supabase REST/Realtime API와 통신
- URL과 publishable(anon) key는 클라이언트 코드에 노출되어도 안전하도록 설계된 값이며, RLS 정책이 실제 접근 범위를 제어합니다

## 기술 스택

- HTML5 / CSS3 (커스텀 프로퍼티, 미디어 쿼리)
- Vanilla JavaScript (프레임워크 없음)
- [Supabase](https://supabase.com) (Postgres, Auth 없는 anon 접근, Realtime)
- Google Fonts (Playfair Display, Noto Sans KR)
