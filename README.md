# Climate Tech Startup Radar

카카오임팩트 임팩트클라이밋 기후테크 스타트업 리서치 대시보드

## 구조

```
dashboard/          → 웹 대시보드 (GitHub Pages로 배포)
knowledge-base/     → 6개 리서치 에이전트 산출물
agents/             → 에이전트 실행 프롬프트 템플릿
reports/            → 종합 리포트
```

## 대시보드 로컬 실행

```bash
open dashboard/index.html
```

## 월간 업데이트 방법

1. Claude Code에서 리서치 에이전트 실행 → `knowledge-base/` 업데이트
2. `dashboard/index.html`의 `STARTUPS` 배열 업데이트
3. git commit & push → GitHub Pages 자동 반영

## GitHub Pages 배포

Settings → Pages → Source: `main` branch, `/dashboard` folder
