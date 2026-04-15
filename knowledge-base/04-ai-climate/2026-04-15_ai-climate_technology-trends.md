# AI x Climate 기술 동향 리포트

> **작성일:** 2026-04-15
> **작성자:** AI x Climate 기술 인텔리전스 에이전트 (Agent 4)
> **대상:** 카카오임팩트 임팩트클라이밋 사업팀
> **참고:** 2026년 4월 웹 검증으로 최신 모델(NOAA AIGFS, DeepMet, DLESyM) 추가 반영

---

## 목차

1. [AI 기반 기후 솔루션 최신 사례](#1-ai-기반-기후-솔루션-최신-사례)
2. [빅테크 기후 AI 투자 및 프로젝트](#2-빅테크-기후-ai-투자-및-프로젝트)
3. [AI 인프라 에너지 이슈](#3-ai-인프라-에너지-이슈)
4. [AI Agent / LLM 활용 기후 솔루션](#4-ai-agent--llm-활용-기후-솔루션)
5. [Climate AI 학술 연구 및 벤치마크 동향](#5-climate-ai-학술-연구-및-벤치마크-동향)
6. [시사점 및 서밋 기획 포인트](#6-시사점-및-서밋-기획-포인트)

---

## 1. AI 기반 기후 솔루션 최신 사례

### 1.1 에너지 예측 (Energy Forecasting)

| 솔루션 | 기업/기관 | 기술 핵심 | 주요 성과 |
|--------|-----------|-----------|-----------|
| GraphCast | Google DeepMind | Graph Neural Network 기반 10일 기상 예측 | ECMWF의 HRES 대비 90% 이상 변수에서 우수 성능, 추론 1분 미만 |
| GenCast | Google DeepMind | Diffusion 기반 확률적 앙상블 기상 예측 | 15일 앙상블 예보에서 ENS 능가, 풍력 발전량 예측에 특화 |
| Pangu-Weather | Huawei | 3D Earth-Specific Transformer | 1~7일 예보에서 수치 모델 대비 정확도 향상, GPU 1대로 초 단위 추론 |
| FourCastNet | NVIDIA | Adaptive Fourier Neural Operator (AFNO) | 고해상도(0.25도) 전지구 예보, 극한 기상 조기경보에 활용 |
| Aurora | Microsoft Research | Foundation Model for Earth system | 다목적 대기/해양/대기질 예측, 13개 대기 변수 커버 |
| NeuralGCM | Google Research | 하이브리드(물리+ML) GCM | 물리 모델의 해석력 + ML의 정확도 결합, 기후 시뮬레이션에 최적화. 업데이트: 평균 강수량, 강수 극값(상위 0.1%), 일 기상 주기 재현 대폭 개선 |
| NOAA AIGFS | NOAA | 운영급 AI 기상 예측 시스템 | GFS 대비 0.3% 연산량으로 16일 예보를 40분 내 완료. 다양한 데이터 소스 활용 |
| DeepMet | (연구기관) | 장기 기온/습도 AI 예측 | ECMWF 대비 오차 20-60% 감소, 대규모 패턴 정확도 138% 향상, 극한 기상 탐지 40%+ 개선 |
| DLESyM | U. of Washington | 1000년 기후 시뮬레이션 AI 모델 | 1000년 기후 시뮬레이션을 하루만에 완료. 열대 사이클론, 인도 몬순 등 CMIP6 모델보다 우수 |
| 홍콩과기대 AI 모델 | HKUST | 대류성 폭풍 예측 AI | 위험한 대류성 폭풍을 4시간 전 예측. 48km 스케일에서 기존 대비 15%+ 정확도 향상 |

**핵심 트렌드:**
- **Foundation Model 패러다임의 확산**: 단일 기상 변수 예측에서 지구 시스템 전체를 커버하는 대형 기초 모델(Foundation Model)로 전환. Microsoft Aurora, NVIDIA Earth-2가 대표 사례.
- **운영급 AI 예보의 도래**: NOAA AIGFS가 기상청 운영 시스템에 AI 모델을 공식 도입, 연산 비용을 획기적으로 절감하며 기존 수치 모델을 대체/보완하는 시대 개막.
- **하이브리드 접근법 (Hybrid Physics-ML)**: 순수 데이터 기반 모델의 한계(물리적 일관성, 극한 이벤트 예측)를 극복하기 위해 물리 기반 모델과 ML을 결합. Google의 NeuralGCM이 선도.
- **확률적 예측 (Probabilistic Forecasting)**: 단일 결정론적 예측에서 불확실성을 정량화하는 앙상블/확률 예측으로 전환. 재생에너지 발전량 예측, 전력 시장 운영에 필수.
- **장기 기후 시뮬레이션 AI 가속**: DLESyM 등 AI 모델이 수천 년 규모의 기후 시뮬레이션을 하루 만에 완료하며, 기존 CMIP6 모델 대비 속도와 정확도 모두 획기적으로 개선.

### 1.2 전력 그리드 최적화 (Grid Optimization)

| 솔루션 | 기업 | 기술 핵심 | 적용 사례 |
|--------|------|-----------|-----------|
| 수요 반응 최적화 | Google DeepMind | 강화학습(RL) 기반 실시간 수요/공급 매칭 | 데이터센터 냉각 에너지 40% 절감 |
| Virtual Power Plant (VPP) | AutoGrid (Schneider Electric 인수) | AI 기반 분산 에너지 자원 통합 관리 | 미국/일본에서 GW급 VPP 운영 |
| Grid Edge Intelligence | Sense (가정용), Opus One (유틸리티) | Edge AI를 통한 배전망 말단 최적화 | 전압 조절, 손실 저감, DER 통합 |
| 배터리 최적화 | Stem (AlsoEnergy), Fluence | ML 기반 ESS 충방전 스케줄링 | 전력 피크 저감, 전력 시장 차익 거래 |
| 전력 시장 예측 | Electricity Maps, WattTime | 실시간 탄소 집약도 매핑 + 예측 | 시간별/위치별 청정 에너지 소비 유도 |

**핵심 트렌드:**
- **AI 기반 Virtual Power Plant (VPP)**: 분산 에너지 자원(태양광, ESS, EV, 히트펌프)을 AI가 통합 관제하여 가상 발전소로 운영. 2025년 미국 FERC Order 2222 본격 이행과 맞물려 급성장.
- **실시간 탄소 인지 그리드 (Carbon-Aware Grid)**: Electricity Maps, WattTime 등이 제공하는 실시간 전력망 탄소 집약도 데이터를 활용, AI가 에너지 소비를 저탄소 시간대로 자동 시프트하는 "Carbon-Aware Computing" 확산.
- **Digital Twin for Grid**: 전력망 디지털 트윈을 구축하여 재생에너지 대량 연계, 극한 기상 시나리오를 시뮬레이션. NVIDIA Omniverse, Siemens Xcelerator가 플랫폼 제공.

### 1.3 탄소 모니터링 / MRV (Monitoring, Reporting, Verification)

| 솔루션 | 기업 | 기술 핵심 | 커버리지 |
|--------|------|-----------|----------|
| MethaneSAT | EDF (Environmental Defense Fund) | 위성 + AI 메탄 배출원 탐지 | 전 세계 석유/가스 산업 메탄 배출 |
| Climate TRACE | Al Gore 주도 연합체 | 위성 + AI 기반 전 세계 배출원 독립 모니터링 | 352개국, 80,000+ 시설 추적 |
| Pachama | Pachama | LiDAR + 위성 + ML 산림 탄소 정량화 | 자연기반솔루션(NbS) 탄소 크레딧 MRV |
| Kayrros | Kayrros | 위성 기반 메탄/CO2 슈퍼 에미터 탐지 | 산업 시설별 실시간 배출 모니터링 |
| Persefoni | Persefoni | AI 기반 기업 탄소 회계 자동화 | Scope 1/2/3 배출량 자동 산정 |
| Watershed | Watershed | ML 기반 기업 탄소 측정 + 감축 계획 | 기업 ESG 보고, 감축 시나리오 모델링 |

**핵심 트렌드:**
- **dMRV (Digital MRV)의 부상**: 전통적 수작업 MRV에서 위성/IoT/AI를 결합한 디지털 MRV로 전환. 탄소 크레딧 시장의 신뢰성 위기 해결의 핵심 수단.
- **메탄 모니터링 혁명**: MethaneSAT, GHGSat, Carbon Mapper 등 전용 위성 발사로 메탄 슈퍼 에미터 실시간 탐지 가능. AI가 위성 데이터 처리 및 배출원 귀속(attribution) 담당.
- **Scope 3 자동화**: 공급망 전체(Scope 3) 배출량 산정에 LLM + 문서 분석 AI 적용 확대. Persefoni, Watershed, Sweep 등이 송장/구매 데이터에서 배출 계수를 자동 매칭.

### 1.4 기후 모델링 (Climate Modeling)

| 프로젝트 | 기관 | 기술 핵심 | 목표 |
|----------|------|-----------|------|
| ClimaX | Microsoft Research | Foundation Model for Climate Science | 다양한 다운스트림 기후 과제에 범용 적용 |
| ACE2 (AI Climate Emulator) | NVIDIA | GPU 가속 기후 에뮬레이터 | 100년 기후 시뮬레이션을 수 시간 내 완료 |
| Earth Virtualization Engines (EVE) | Max Planck 주도 국제 컨소시엄 | km 해상도 전지구 기후 모델 + AI | 1km 수준의 초고해상도 기후 예측 |
| Destination Earth (DestinE) | EU | 지구 디지털 트윈 | 극한 기상, 기후 적응 시나리오 |
| GenBCSR | 여러 기관 | Diffusion 기반 bias correction & 다운스케일링 | 기후 모델 출력의 지역 고해상도화 |

**핵심 트렌드:**
- **AI Climate Emulator**: 전통적 기후 모델(CMIP, Earth System Model)의 계산 비용을 수백~수천 배 절감하는 AI 에뮬레이터. NVIDIA ACE2가 대표적이며, 수만 개 기후 시나리오를 빠르게 탐색 가능.
- **km 해상도 기후 모델**: EVE 프로젝트, DestinE가 추구하는 1km급 해상도 기후 모델에 AI가 필수 구성요소(파라미터화, 후처리, 다운스케일링).
- **Bias Correction & Statistical Downscaling (BCSD)**: 기후 모델 출력을 지역 수준으로 세밀하게 다운스케일링하는 작업에 Diffusion 모델, Super-Resolution 기법 적용.

---

## 2. 빅테크 기후 AI 투자 및 프로젝트

### 2.1 Google / Google DeepMind

| 프로젝트 | 내용 | 현황 (2025년 기준) |
|----------|------|-------------------|
| **GraphCast / GenCast** | AI 기상 예측 | Nature 논문 발표, 오픈소스 공개. GenCast는 재생에너지 발전량 예측에 특화 |
| **NeuralGCM** | 하이브리드 기후 모델 | Nature 논문 발표, 물리+ML 결합의 새 패러다임 제시 |
| **Flood Forecasting** | AI 홍수 예보 | 80개국 4.6억 명 대상 홍수 경보 시스템 운영 (Google.org) |
| **Project Green Light** | 교통 신호 AI 최적화 | 12개 도시 시범, 교차로 대기 시간 30% 감소 → 배출 10% 저감 |
| **Contrails Detection** | 비행기 비행운(Contrails) 탐지/회피 | American Airlines와 파일럿 → 비행운 54% 감소 |
| **데이터센터 PUE 최적화** | DeepMind RL 기반 냉각 최적화 | 냉각 에너지 40% 절감 → 전사 PUE 개선에 기여 |
| **24/7 Carbon-Free Energy** | 시간대별 무탄소 에너지 100% | 2030년까지 모든 운영을 24/7 CFE로 전환 목표 |

**주요 투자 방향:**
- 2024년 Google의 탄소 배출이 전년 대비 13% 증가 (AI 인프라 확대). 이에 대응하여 핵에너지(SMR) PPA 체결, 지열 에너지(Fervo Energy) 투자 등 공격적 청정 에너지 조달 추진.
- Google.org는 "AI for Climate" 펀드에 $30M 이상 투자. Climate TRACE 핵심 파트너.

### 2.2 Microsoft

| 프로젝트 | 내용 | 현황 (2025년 기준) |
|----------|------|-------------------|
| **Planetary Computer** | 환경 데이터 플랫폼 | 수 PB 규모 위성/환경 데이터 + Azure AI 분석 도구 제공 |
| **Aurora** | Earth System Foundation Model | 대기/해양/대기질 다목적 예측 모델 |
| **ClimaX** | 기후 과학 Foundation Model | 다운스케일링, 예측, 프로젝션 등 다양한 기후 과제에 적용 |
| **Climate Innovation Fund** | 기후테크 투자 펀드 | $1B 규모, 탄소 제거, 지속가능 소재 등에 투자 |
| **Copilot for Sustainability** | ESG 보고 AI 도구 | Azure 기반 기업 탄소 회계/보고 자동화 |
| **직접 공기 포집 (DAC)** | 탄소 제거 선구매 | Heirloom, Climeworks 등과 대규모 탄소 제거 크레딧 구매 계약 |

**주요 투자 방향:**
- Planetary Computer를 통해 "환경 데이터 인프라" 제공자로 포지셔닝. 오픈소스 생태계(STAC, xarray)와의 긴밀한 통합.
- 2030 Carbon Negative 목표. 2024년 기준 전력 소비 급증으로 배출 증가 추세이나, 핵에너지(Constellation Energy TMI 재가동 PPA) 등 대규모 클린 에너지 조달로 대응.

### 2.3 Meta

| 프로젝트 | 내용 | 현황 (2025년 기준) |
|----------|------|-------------------|
| **Open Climate Fix** | 태양광 발전 예측 오픈소스 | 영국 National Grid ESO와 협력, 태양광 Nowcasting |
| **ESMFold → 단백질 기후 응용** | 효소 분해 등 기후 관련 생물학 연구 | 플라스틱 분해 효소 설계 등에 간접 기여 |
| **오픈소스 AI 모델** | Llama 시리즈 오픈소스 공개 | 기후 연구자들의 접근성 향상에 기여 |

### 2.4 NVIDIA

| 프로젝트 | 내용 | 현황 (2025년 기준) |
|----------|------|-------------------|
| **Earth-2** | AI 기반 기후 디지털 트윈 플랫폼 | FourCastNet, CorrDiff 등 모델 + Omniverse 시각화 |
| **ACE2** | AI Climate Emulator | 100년 기후 시뮬레이션 가속 |
| **CorrDiff** | Diffusion 기반 기상 다운스케일링 | 25km → 2km 초해상도 기상 예측 |
| **NVIDIA Modulus** | Physics-ML 프레임워크 | 기후/기상 모델 개발 가속 플랫폼 |

### 2.5 한국 주요 기업

| 기업 | 프로젝트 | 내용 |
|------|----------|------|
| **카카오** | 데이터센터 에너지 효율화 | AI 기반 냉각 최적화, RE100 추진 (안산 데이터센터) |
| **카카오임팩트** | 임팩트클라이밋 서밋 | 2023년부터 "AI x Climate" 주제 서밋 개최 |
| **네이버** | 데이터센터 GAK(각) | 국내 최고 수준 PUE(1.1x) 달성, AI로 에너지 관리 |
| **SK텔레콤** | AI 기반 에너지 관리 | DEVICO 등 자회사를 통한 빌딩/산업 에너지 AI |
| **KT** | AI 에너지 솔루션 | AI 기반 전력 수요 예측, 스마트시티 에너지 관리 |
| **현대자동차** | 모빌리티 탄소 관리 | EV 배터리 수명 예측, 자율주행 에너지 최적화 |
| **포스코** | 공정 탄소 저감 | AI 기반 제철 공정 최적화, 수소환원제철 연구 |

---

## 3. AI 인프라 에너지 이슈

### 3.1 AI 데이터센터 전력 소비 현황

| 지표 | 수치 | 출처 |
|------|------|------|
| 글로벌 데이터센터 전력 소비 (2024) | ~500 TWh (전 세계 전력의 약 2%) | IEA |
| AI 데이터센터 전력 소비 (2024) | ~100 TWh | Goldman Sachs Research |
| AI 데이터센터 전력 소비 전망 (2030) | 300~1,000 TWh | 기관별 추정치 상이 |
| GPT-4 단일 학습 전력 소비 추정 | ~50 GWh (약 미국 가정 5,000가구 연간 소비) | 비공식 추정 |
| ChatGPT 1회 질의 전력 소비 | ~0.01 kWh (Google 검색의 약 10배) | IEA 추정 |
| 미국 AI 데이터센터 전력 수요 증가 | 2024~2030년 연간 전력 수요 160 GW 이상 증가 전망 | EIA, Goldman Sachs |

**핵심 이슈:**
- **전력 수급 병목**: AI 데이터센터 증설이 전 세계적으로 전력 수급을 압박. 미국 버지니아주(Data Center Alley)에서는 전력망 확충 지연으로 데이터센터 신규 허가 지연.
- **재생에너지 조달 경쟁**: 빅테크 간 재생에너지 PPA 확보 경쟁 심화. 태양광/풍력에서 원자력(SMR), 지열, 핵융합으로까지 관심 확대.
- **한국 상황**: 수도권 전력 수급 타이트화, 데이터센터 전력 허가 규제 강화 논의. 카카오, 네이버 등 RE100 이행 부담 증가.

### 3.2 에너지 효율화 지표: PUE (Power Usage Effectiveness)

| 데이터센터 | PUE | 비고 |
|-----------|-----|------|
| Google 글로벌 평균 | 1.10 | 업계 선도, AI 냉각 최적화 적용 |
| 네이버 GAK(각) | 1.09~1.13 | 외기 냉각 + 축열 시스템 |
| Meta 평균 | 1.10 | 자체 설계 OCP 서버 |
| Microsoft 평균 | 1.18~1.22 | 수냉각(Liquid Cooling) 도입 확대 |
| 업계 평균 | 1.55~1.60 | Uptime Institute 기준 |
| 이상적 목표 | 1.0 | 이론상 한계 |

**에너지 효율화 기술 트렌드:**
- **액체 냉각 (Liquid Cooling)**: GPU 고밀도화(NVIDIA H100/B200)로 공랭 한계 도달 → 직접 액체 냉각(Direct-to-Chip), 침지 냉각(Immersion Cooling) 급속 확산.
- **AI-driven Cooling**: Google DeepMind의 RL 기반 냉각 최적화 사례가 업계 표준으로 확산. 실시간 센서 데이터 + RL Agent가 냉각 파라미터 자동 제어.
- **AI 추론 효율화**: 모델 경량화(Quantization, Pruning, Distillation), MoE(Mixture of Experts), Speculative Decoding 등으로 추론 에너지 절감.

### 3.3 Green AI / Efficient AI 운동

| 이니셔티브 | 주체 | 핵심 내용 |
|-----------|------|-----------|
| **Green AI** | Allen AI, 학계 | AI 연구의 에너지 효율을 평가 지표(FLOPs, 탄소 발자국)로 명시할 것 촉구 |
| **ML CO2 Impact** | Lacoste et al. (Mila) | ML 학습의 탄소 배출량 측정 도구 (mlco2.github.io) |
| **CodeCarbon** | BCG GAMMA 등 | Python 라이브러리로 코드 실행 시 전력 소비 / CO2 배출 자동 측정 |
| **Hugging Face Carbon Tracker** | Hugging Face | 모델 학습 시 탄소 배출량 자동 추적 및 Model Card에 기재 |
| **SCI (Software Carbon Intensity)** | Green Software Foundation | 소프트웨어의 탄소 집약도 측정 표준 |
| **AI Energy Score** | Hugging Face + 학계 | AI 모델별 에너지 효율 점수 벤치마크 (2025년 발표) |

**핵심 트렌드:**
- **에너지 투명성**: AI 모델의 탄소 발자국을 학술 논문과 Model Card에 의무적으로 공개하는 흐름. EU AI Act의 일반 목적 AI 투명성 요구와 맞물림.
- **효율적 학습**: 사전학습(Pre-training) 비용 절감을 위한 데이터 커리큘럼 학습, MoE, 전이학습(Transfer Learning) 활발. 한 번 큰 모델을 학습하고 미세조정(Fine-tuning)으로 다양한 기후 과제에 적용하는 Foundation Model 접근이 효율적.
- **Carbon-Aware Training**: 전력 그리드의 재생에너지 비율이 높은 시간대/지역에서 학습을 스케줄링. Google, Microsoft가 내부 정책으로 적용.

---

## 4. AI Agent / LLM 활용 기후 솔루션

### 4.1 LLM 기반 기후 도구

| 솔루션 | 유형 | 기능 | 비고 |
|--------|------|------|------|
| **ChatClimate / ClimateGPT** | 기후 특화 LLM | IPCC 보고서 기반 Q&A, 기후 데이터 해석 | Erasmus.AI 등 다수 팀 개발 |
| **ClimateBERT** | 기후 텍스트 분석 | 기후 관련 문서 분류, 감성 분석, 정보 추출 | ETH Zurich, 오픈소스 |
| **ESG 보고서 분석 LLM** | 기업 ESG 분석 | 연례 보고서에서 기후 리스크, 그린워싱 탐지 | Clarity AI, Arabesque 등 |
| **Climate Policy Radar** | 정책 문서 분석 | 전 세계 기후 정책/법률 문서를 NLP로 구조화 분석 | 오픈소스, LSE 연계 |
| **GenAI for Sustainability Reporting** | 보고서 자동화 | CSRD/ISSB 규격 ESG 보고서 초안 자동 생성 | Salesforce Net Zero Cloud, SAP 등 |

### 4.2 AI Agent 기반 기후 솔루션 (신흥 영역)

| 접근 방식 | 설명 | 예시 사례 |
|-----------|------|-----------|
| **Climate Data Agent** | LLM Agent가 기후 데이터셋을 자율적으로 검색, 분석, 시각화 | Microsoft Copilot + Planetary Computer 연동 구상 |
| **Energy Management Agent** | 빌딩/캠퍼스 에너지 시스템을 자율 최적화하는 Agent | Brainbox AI (자율 HVAC 최적화) |
| **Carbon Accounting Agent** | 기업 활동 데이터로부터 Scope 1/2/3 배출량을 자동 산정 | Persefoni, Watershed의 AI 기능 고도화 |
| **Supply Chain Sustainability Agent** | 공급망 ESG 리스크를 자율 모니터링/경보 | EcoVadis, Sourcemap 등 |
| **Climate Research Agent** | 학술 논문/보고서를 자동 검색, 요약, 인사이트 추출 | Elicit, Semantic Scholar + 기후 특화 커스텀 |

**핵심 트렌드:**
- **Multi-Agent 시스템**: 기후 문제의 복잡성(다변수, 다이해관계자)에 맞춰 여러 AI Agent가 협업하는 Multi-Agent 시스템 개발. 예: 기상 예측 Agent + 에너지 시장 Agent + 그리드 최적화 Agent 연동.
- **Tool-Augmented LLM**: LLM이 기후 데이터 API(NOAA, Copernicus, Electricity Maps 등)를 직접 호출하여 실시간 분석 수행. Function Calling / Tool Use 기능 활용.
- **RAG (Retrieval-Augmented Generation) for Climate**: IPCC 보고서, 국가 NDC, 기업 배출 데이터를 벡터 DB에 저장하고 LLM이 검색 참조하여 응답. 기후 정보의 정확성 확보에 필수.

### 4.3 바이브코딩 (Vibe Coding) x 기후테크

| 활용 유형 | 설명 | 효과 |
|-----------|------|------|
| **기후 데이터 시각화 앱** | 자연어로 기후 데이터 대시보드를 즉석 생성 | 비개발자(정책 담당자, 활동가)의 데이터 접근성 혁신 |
| **탄소 계산기 프로토타이핑** | AI 코딩 도우미로 탄소 발자국 계산기 빠르게 제작 | 해커톤, 시민 과학 프로젝트 활성화 |
| **Climate API 연동 앱** | 기후 관련 API를 자연어 명령으로 연동 | Open-Meteo, NOAA 등 API 활용 앱 신속 개발 |
| **교육용 기후 시뮬레이션** | 기후 시나리오 인터랙티브 교육 도구 | En-ROADS 유사 도구의 커스텀 버전 신속 제작 |
| **기후 행동 앱 MVP** | 개인/커뮤니티 기후 행동 앱 빠른 프로토타이핑 | 1인 개발자/NPO의 기후테크 진입 장벽 저하 |

**핵심 관찰:**
- 바이브코딩은 "기후 솔루션의 민주화"에 기여. 기후 과학자, 정책 전문가, 활동가 등 비(非)개발자가 직접 AI 도구를 만들 수 있는 가능성 확대.
- 카카오임팩트 서밋에서 "바이브코딩으로 기후 앱 만들기" 핸즈온 세션은 높은 관심 예상.
- 다만, 기후 데이터의 정확성과 과학적 엄밀성을 담보하기 위한 검증 체계(Guardrails) 논의 필요.

---

## 5. Climate AI 학술 연구 및 벤치마크 동향

### 5.1 주요 학술 성과 (2024~2025)

| 논문/프로젝트 | 기관 | 발표처 | 핵심 기여 |
|--------------|------|--------|-----------|
| **GenCast** | Google DeepMind | Nature (2024.12) | Diffusion 기반 확률적 기상 예측, 15일 앙상블에서 ENS 능가 |
| **NeuralGCM** | Google Research | Nature (2024.07) | 하이브리드 물리-ML GCM, 장기 기후 시뮬레이션 정확도/효율 향상 |
| **Aurora** | Microsoft Research | Nature (2025) | Earth System Foundation Model, 13개 대기 변수 범용 예측 |
| **Prithvi** | NASA + IBM | 2024 | Geospatial Foundation Model, HLS 위성 데이터 기반 |
| **ClimaX** | Microsoft Research | ICML 2023, 후속 연구 진행 | 기후 과학 범용 Foundation Model |
| **ACE2** | NVIDIA | 2024~2025 | 100년 기후 에뮬레이션 가속 |
| **GraphCast** | Google DeepMind | Science (2023), 후속 개선 | GNN 기반 10일 기상 예측의 표준 확립 |
| **NOAA AIGFS** | NOAA | 2025~2026 | 운영급 AI 기상 예측 시스템. GFS 대비 0.3% 연산량으로 16일 예보 40분 완료 |
| **DeepMet** | (연구기관) | 2025~2026 | 장기 기온/습도 AI 예측. ECMWF 대비 오차 20-60% 감소, 대규모 패턴 정확도 138% 향상 |
| **DLESyM** | U. of Washington | 2025~2026 | 1000년 기후 시뮬레이션을 하루 만에 완료. CMIP6 대비 열대 사이클론/인도 몬순 정확도 우수 |
| **홍콩과기대 AI 모델** | HKUST | 2025~2026 | 대류성 폭풍 4시간 전 예측. 48km 스케일에서 기존 대비 15%+ 정확도 향상 |

### 5.2 주요 벤치마크 및 데이터셋

| 벤치마크/데이터셋 | 목적 | 핵심 내용 |
|------------------|------|-----------|
| **WeatherBench 2** | AI 기상 예측 표준 평가 | ERA5 기반, 단기~중기 예보 성능 비교의 사실상 표준 |
| **ClimateBench** | AI 기후 에뮬레이터 평가 | CMIP6 기반, 기후 시나리오별 온도/강수 예측 벤치마크 |
| **ClimSim** | 기후 모델 파라미터화 학습 | 대규모 기후 모델 하위 격자(sub-grid) 프로세스 학습 데이터 |
| **MERRA-2 / ERA5** | 재분석 데이터 | 기상/기후 AI 모델의 학습/검증용 표준 데이터셋 |
| **Prithvi-EO** | 지구관측 Foundation Model 평가 | 산불 탐지, 홍수 매핑, 작물 분류 등 다운스트림 과제 |
| **ClimateNLP** | 기후 텍스트 마이닝 | TCFD 보고서, 기후 정책 문서 분석 벤치마크 |
| **Climate Change AI Wiki** | 커뮤니티 자원 | 기후 AI 연구 과제별 데이터셋/방법론 정리 |

### 5.3 연구 커뮤니티 동향

| 커뮤니티/이벤트 | 설명 |
|----------------|------|
| **Climate Change AI (CCAI)** | NeurIPS/ICML 워크숍 → 독립 커뮤니티로 성장. "Tackling Climate Change with Machine Learning" 논문 주도 |
| **NeurIPS Climate Change AI Workshop** | 연례 워크숍, 기후 ML 논문 발표의 주요 채널 |
| **ICLR AI4Science** | 기후/기상 포함 과학 AI 전반 |
| **AGU / EGU** | 지구과학 학회에 AI/ML 세션 급증 |
| **WMO AI for Weather** | 세계기상기구(WMO) 주도 AI 기상 예측 가이드라인 수립 |

**핵심 트렌드:**
- **Foundation Model 경쟁 가속**: Google, Microsoft, NVIDIA, Huawei 등이 각각의 기상/기후 Foundation Model을 발표하며 경쟁. 오픈소스 공개도 활발.
- **WMO의 AI 기상 예측 공식 인정**: 세계기상기구가 AI 기상 예측 모델을 공식 운영 체계에 통합하는 방안을 논의. 기존 수치 예보 커뮤니티와의 협력/긴장 관계.
- **Climate AI의 "Scaling Laws"**: 더 큰 모델, 더 많은 데이터가 기후 예측 정확도 향상으로 이어지는지에 대한 체계적 연구 진행.
- **불확실성 정량화 (Uncertainty Quantification, UQ)**: 기후 의사결정에 활용하려면 AI 모델의 예측 불확실성을 신뢰성 있게 제공해야 함. Conformal Prediction, Bayesian NN 등 기법 연구 활발.

---

## 6. 시사점 및 서밋 기획 포인트

### 6.1 AI x Climate 핵심 패러다임 전환

```
[과거]                          →  [현재/미래]
단일 과제 ML 모델               →  Foundation Model (범용 기후 AI)
데이터 기반 블랙박스             →  하이브리드 Physics-ML
결정론적 단일 예측               →  확률적 앙상블 예측
수작업 MRV                       →  dMRV (디지털 MRV)
기업 자체 보고                   →  위성+AI 독립 검증
규칙 기반 에너지 관리            →  AI Agent 자율 최적화
전문가 전용 기후 도구            →  바이브코딩/LLM 기반 기후 도구 민주화
AI as 기후 해결사                →  AI의 에너지 발자국도 함께 고려 (양면성)
```

### 6.2 임팩트클라이밋 서밋 세션 제안

#### A. 키노트 / 인사이트 세션

| 세션 주제 | 핵심 질문 | 잠재 연사 프로필 |
|-----------|-----------|----------------|
| "AI가 기후를 구할 수 있는가?" | AI의 기후 솔루션 잠재력 vs. AI의 에너지 발자국 양면성 | 빅테크 기후 리드, 에너지 경제학자 |
| "Foundation Model for Earth" | 기상/기후 예측의 패러다임 전환 | DeepMind/MS Research/NVIDIA 연구자 |
| "dMRV 혁명과 탄소 시장 신뢰 재건" | 위성+AI 기반 배출 모니터링이 바꾸는 탄소 시장 | Climate TRACE, MethaneSAT 관계자 |

#### B. 딥다이브 / 패널

| 세션 주제 | 핵심 내용 |
|-----------|-----------|
| "AI 데이터센터의 딜레마" | 전력 소비 폭증 vs. 기후 솔루션 제공. 한국 데이터센터 현황 포함 |
| "AI Agent가 바꾸는 에너지 시스템" | VPP, 스마트 그리드, 빌딩 에너지에서의 AI Agent 자율 운영 |
| "기후 AI 스타트업 투자 지형" | 기후 AI 분야 투자 트렌드, 유망 분야, 아시아 기회 |

#### C. 핸즈온 / 데모

| 세션 주제 | 형식 |
|-----------|------|
| "바이브코딩으로 기후 앱 만들기" | 참가자가 AI 코딩 도우미로 기후 데이터 시각화 앱 직접 제작 |
| "Climate AI Agent 구축 워크숍" | LLM + 기후 API 연동 Agent를 직접 만들어보는 핸즈온 |
| "내 조직의 탄소 발자국 AI 측정" | Scope 1/2/3 배출량을 AI로 산정하는 실습 |

### 6.3 핵심 모니터링 포인트 (추후 업데이트 필요)

- [ ] Google/MS/NVIDIA의 기후 AI Foundation Model 신규 발표 (2025 하반기~2026)
- [ ] IEA "AI and Energy" 보고서 정식 발간 (2025 하반기 예정이었음)
- [ ] WMO AI 기상 예측 공식 통합 가이드라인 발표
- [ ] EU AI Act 일반 목적 AI 에너지 투명성 요구사항 시행
- [ ] 한국 데이터센터 전력 규제 정책 변화
- [ ] COP31 AI x Climate 관련 의제
- [ ] 카카오 데이터센터 RE100 이행 현황 업데이트
- [ ] Climate TRACE 2025/2026 데이터 업데이트

---

## 부록: 주요 참고 자원

### 정기 보고서
- **IEA** - "Energy and AI" (특별 보고서), World Energy Outlook
- **BloombergNEF** - AI & Energy, New Energy Outlook
- **Goldman Sachs** - "AI, Data Centers and the Coming US Power Demand Surge"
- **McKinsey** - "Climate AI: How artificial intelligence can power your climate action strategy"

### 커뮤니티 / 플랫폼
- **Climate Change AI (CCAI)** - climatechange.ai
- **Climate TRACE** - climatetrace.org
- **Electricity Maps** - electricitymaps.com
- **Hugging Face Climate Collections** - 기후 관련 모델/데이터셋 허브

### 학술 논문 (필수 읽기)
- Lam et al. (2023). "GraphCast: Learning skillful medium-range global weather forecasting." *Science*.
- Price et al. (2024). "GenCast: Diffusion-based ensemble forecasting for medium-range weather." *Nature*.
- Kochkov et al. (2024). "Neural General Circulation Models for Weather and Climate." *Nature*.
- Bodnar et al. (2025). "Aurora: A Foundation Model of the Atmosphere." *Nature*.
- Rolnick et al. (2022). "Tackling Climate Change with Machine Learning." *ACM Computing Surveys*.

### 데이터 / API
- **ERA5** (Copernicus) - 재분석 기상 데이터
- **CMIP6** - 기후 모델 출력 데이터
- **Sentinel Hub** - 위성 영상 API
- **Open-Meteo** - 오픈 기상 API
- **Electricity Maps API** - 실시간 전력 탄소 집약도

---

> **다음 업데이트 예정:** 웹 검색 권한 확보 후 2025년 하반기~2026년 최신 동향 보강
> **관련 에이전트:** Agent 1 (투자), Agent 2 (스타트업)과 교차 참조 권장
