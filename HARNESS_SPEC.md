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
3. 하네스 헌법 (Development Rules)
AI(Cursor, Claude Code)를 활용해 개발할 때 반드시 준수해야 할 규칙:

규칙 1 (보안): 모든 데이터 응답 시 '병원 내부 자료'임을 명시하고 외부 유출 방지 로직 포함.

규칙 2 (RAG 검증): 답변의 근거 문서(Source)가 불분명할 경우 "정확한 안내를 위해 해당 부서에 문의하세요"라고 답변할 것.

규칙 3 (일관성): UI 라이브러리는 lucide-react 아이콘과 shadcn/ui를 기본으로 사용함.

4. 검증 루프 (Verification)
모든 API 엔드포인트는 호출 성공률 99% 이상이어야 함.

채팅 응답 속도(TTFB)는 1초 이내여야 함.
