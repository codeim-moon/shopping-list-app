# 🛒 쇼핑 리스트 앱

바닐라 HTML/CSS/JavaScript로 만든 간단한 쇼핑 리스트 웹 앱입니다. 별도의 빌드 과정이나 프레임워크 없이 단일 HTML 파일로 동작합니다.

## 기능

- 물건 추가 (버튼 클릭 또는 Enter 키)
- 항목 체크/체크 해제 (구매 완료 표시)
- 항목 삭제
- 체크된 항목 일괄 삭제
- `localStorage`를 이용한 데이터 저장 (새로고침해도 목록 유지)
- 라이트/다크 모드 자동 대응 (`prefers-color-scheme`)

## 실행 방법

`shopping-list/index.html` 파일을 브라우저로 열면 바로 사용할 수 있습니다.

```bash
# 예시 (Windows)
start shopping-list/index.html
```

## 기술 스택

- HTML5
- CSS3 (커스텀 프로퍼티, 미디어 쿼리)
- Vanilla JavaScript (외부 라이브러리 없음)
