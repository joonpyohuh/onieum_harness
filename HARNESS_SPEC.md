1. 시각적 기준 (Frontend Reference)
UI/UX: v0.dev 링크의 컴포넌트 구조를 100% 따름.

핵심 동작: 홈화면 카드 클릭 시 각 카테고리 탭으로 전환, 채팅 입력 시 전체 화면 모드로 전환되는 UX 유지.

2. 백엔드 데이터 규격 (API Contract)
시설/주차/행정/공지: 하드코딩하지 말고, 아래와 같은 JSON 구조를 가진 API를 호출해서 렌더링할 것.
{
  "category": "facility",
  "tabs": ["층별 안내", "편의시설"],
  "content": [
    { "title": "B1 장례식장/매점", "description": "엘리베이터 3호기 이용" }
  ]
}
채팅(RAG): 사용자의 질문을 백엔드 /api/chat으로 전송하고, Streaming 방식으로 응답을 받아올 것.
