# Impact Climate Research Hub

카카오임팩트 임팩트클라이밋 기후테크 생태계 리서치 대시보드

## 월간 업데이트 명령어

사용자가 "월간 기후테크 업데이트 실행해줘" 또는 "전체 리서치 스캔" 이라고 하면 아래 작업을 순차 수행:

### 1단계: 웹 검색으로 6개 영역 최신 데이터 수집
WebSearch를 사용하여:
- 글로벌 기후테크 투자 동향 (투자액, 주요 딜, 트렌드)
- 기후테크 스타트업 최신 뉴스 (투자유치, 신규 창업, M&A)
- 글로벌/한국 기후 정책 변화 (CBAM, K-ETS, NDC 등)
- AI × Climate 기술 최신 동향 (새 모델, 빅테크 프로젝트)
- 기후테크 생태계 변화 (새 펀드, 협회, 프로그램)
- 글로벌 기후 이벤트 및 보고서 발간

### 2단계: Knowledge Base 업데이트
`knowledge-base/` 아래 6개 폴더에 새 월간 리포트 생성
파일명 규칙: `YYYY-MM-DD_[카테고리]_[주제].md`

### 3단계: 대시보드 업데이트
`dashboard/index.html`의 데이터 업데이트 (투자 수치, 주요 딜 테이블, 정책 카드, AI 모델 테이블, 이벤트 타임라인, 스타트업 JS 배열 등)

### 4단계: GitHub 배포
```bash
git add -A && git commit -m "Monthly research update YYYY-MM" && git push
```
GitHub Pages 자동 배포: https://josang-impact.github.io/climatetech-research-hub/

### 5단계: 슬랙 알림
#1-테크임팩트 채널(C0ALH7FG1MF)에 요약 메시지 전송:
```
*🌏 Impact Climate Research Hub — [월] 월간 업데이트 완료*
• 투자: [핵심 1줄]
• 스타트업: [핵심 1줄]
• 정책: [핵심 1줄]
• AI×Climate: [핵심 1줄]
• 생태계: [핵심 1줄]
• 이벤트: [핵심 1줄]
*대시보드:* https://josang-impact.github.io/climatetech-research-hub/
```

## 리서치 에이전트 참고
- 에이전트 설계: `RESEARCH-AGENTS.md`
- 실행 프롬프트: `agents/agent-prompts.md`
- 대시보드: `dashboard/index.html`
- GitHub: https://github.com/josang-impact/climatetech-research-hub

## 브랜드
- Kakao Yellow: #FFCD00
- Dark theme: impactclimate.net 참조
- 폰트: Pretendard Variable
