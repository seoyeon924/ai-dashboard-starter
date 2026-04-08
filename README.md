# AI Dashboard Starter Kit

CSV 파일 하나로 분석 → KPI → 대시보드까지 자동으로 만드는 7-Step AI 파이프라인입니다.

Claude Code + 이 레포만 있으면 됩니다.

---

## 빠른 시작

### 1. 레포 클론

```bash
git clone https://github.com/seoyeon924/ai-dashboard-starter.git
cd ai-dashboard-starter
```

### 2. 내 데이터 넣기

```bash
# runs/latest/input/ 폴더에 CSV를 복사
cp 내_데이터.csv runs/latest/input/
```

`data/sample_sales.csv` — 연습용 샘플 데이터입니다. 먼저 이걸로 돌려보세요.

### 3. Claude Code에서 실행

```
파이프라인 실행해줘
```

끝입니다. 7단계가 순서대로 실행되며 `runs/latest/outputs/` 에 결과물이 생성됩니다.

---

## 결과물

```
runs/latest/outputs/
├── 01_dataset_profile.md    # 데이터 구조 파악
├── 02_eda_report.md         # 탐색적 분석
├── 03_problem_definition.md # 핵심 질문 정의
├── 04_kpi_summary.md        # KPI 정의 및 현재값
├── 05_analysis_report.md    # 분석 인사이트
├── 06_dashboard.html        # ← 여기가 최종 대시보드
└── 07_executive_report.md   # 임원 보고서
```

브라우저에서 `06_dashboard.html`을 열면 완성된 대시보드가 나타납니다.

---

## 폴더 구조

```
ai-dashboard-starter/
├── CLAUDE.md                     # 파이프라인 규칙 (Claude가 읽는 파일)
├── .claude/
│   ├── agents/                   # 7개 AI 에이전트 역할 정의
│   │   ├── data-ingestion.md
│   │   ├── eda.md
│   │   ├── problem.md
│   │   ├── metrics.md
│   │   ├── analysis.md
│   │   ├── dashboard.md
│   │   └── report.md
│   └── skills/
│       └── visualize/SKILL.md    # 대시보드 디자인 시스템
├── data/
│   └── sample_sales.csv          # 연습용 샘플 데이터
└── runs/
    └── latest/
        ├── input/                # ← 여기에 CSV 넣기
        └── outputs/              # ← 결과물 자동 생성
```

---

## 내 데이터로 바꾸려면

CSV 컬럼이 달라도 괜찮습니다. `@data-ingestion` 에이전트가 컬럼 구조를 먼저 파악합니다.

잘 작동하는 데이터 형식:
- 날짜 컬럼 (월별/일별 추세 분석)
- 수치 컬럼 (매출, 수량, 비용 등)
- 범주 컬럼 (지역, 카테고리, 담당자 등)

---

## 필요한 것

- [Claude Code](https://claude.ai/code) (Claude 계정 필요)
- 이 레포

---

## 라이선스

MIT
