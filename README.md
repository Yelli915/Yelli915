# 🟢 Status: Active | Yelli915

> 결과가 잘 나왔을 때 "진짜 잘 된 건가?"를 한 번 더 확인하는 AI 엔지니어입니다.

[![Naver Blog](https://img.shields.io/badge/Naver_Blog-yelli915-03CF5D?style=for-the-badge&logo=naver&logoColor=white)](https://blog.naver.com/yeri8791)
[![Tistory](https://img.shields.io/badge/Tistory-yelli915-EA5328?style=for-the-badge&logo=tistory&logoColor=white)](https://yelli915.tistory.com/)

---

## 💡 Engineering Focus & Problem Solving

* **원인을 나눠서 찾기**: 모델이 이상하게 동작하면 재학습부터 하지 않고, 학습 쪽 변수와 평가 쪽 변수를 나눠 한 번에 하나씩 바꿔 봅니다. sLLM 프로젝트에서 답변이 깨지던 원인이 학습이 아니라 평가 옵션이었다는 걸 이렇게 찾았습니다.
* **테스트 통과의 의미 확인하기**: 응급실 에이전트 프로젝트에서 테스트 140개가 통과했는데도 핵심 모듈 테스트가 실행되지 않고 있었습니다. 그 뒤로 통과 수보다 무엇이 실제로 실행됐는지를 먼저 봅니다.
* **원본과의 대응 관계 유지하기**: ReadWith에서 EPUB을 LLM 입력으로 바꿀 때 사라지는 위치 정보를 locator 좌표계로 보존했습니다.
* **한계 기록하기**: 남은 문제와 측정하지 못한 항목은 수치와 함께 문서에 남깁니다.

---

## 🏆 Verified Impact & Awards

* **🥇 최우수상 수상** — **ReadWith (캡스톤디자인)**
  * EPUB 문단 좌표계와 관계 변화량(Delta) 누적 방식으로, 독서 위치까지만 보여주는 그래프 구현
* **🏅 장려상 수상** — **의료 빅데이터 분석 프로젝트**
  * 임상 데이터의 결측치·이상치를 정리하고 예측 모델링과 시각화로 위험 인자 분석

---

## ⚙️ Engineering Toolset

| Category | Problem Solving Tools |
| :--- | :--- |
| **Frontend & Visualization** | ![React](https://img.shields.io/badge/React-61DAFB?style=flat-square&logo=react&logoColor=black) ![Next.js](https://img.shields.io/badge/Next.js-000000?style=flat-square&logo=nextdotjs&logoColor=white) ![Vue.js](https://img.shields.io/badge/Vue.js_3-4FC08D?style=flat-square&logo=vuedotjs&logoColor=white) ![Streamlit](https://img.shields.io/badge/Streamlit-FF4B4B?style=flat-square&logo=streamlit&logoColor=white) ![Cytoscape.js](https://img.shields.io/badge/Cytoscape.js-EA5328?style=flat-square) ![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-06B6D4?style=flat-square&logo=tailwindcss&logoColor=white) |
| **Backend & Architecture** | ![Java](https://img.shields.io/badge/Java_21-ED8B00?style=flat-square&logo=openjdk&logoColor=white) ![Spring Boot](https://img.shields.io/badge/Spring_Boot_3-6DB33F?style=flat-square&logo=springboot&logoColor=white) ![Spring Cloud](https://img.shields.io/badge/Spring_Cloud-6DB33F?style=flat-square&logo=spring&logoColor=white) ![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white) |
| **Message & Database** | ![Kafka](https://img.shields.io/badge/Kafka-231F20?style=flat-square&logo=apachekafka&logoColor=white) ![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white) ![MariaDB](https://img.shields.io/badge/MariaDB-003545?style=flat-square&logo=mariadb&logoColor=white) ![SQLite](https://img.shields.io/badge/SQLite-003B57?style=flat-square&logo=sqlite&logoColor=white) |
| **AI & Orchestration** | ![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white) ![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white) ![HuggingFace](https://img.shields.io/badge/Transformers_·_PEFT_·_TRL-FFD21E?style=flat-square&logo=huggingface&logoColor=black) ![LangGraph/Agent](https://img.shields.io/badge/LangGraph_·_LangChain-FF6F00?style=flat-square) ![Pydantic](https://img.shields.io/badge/Pydantic-E92063?style=flat-square&logo=pydantic&logoColor=white) ![Google Gemini](https://img.shields.io/badge/Gemini_API-8E75B2?style=flat-square&logo=googlegemini&logoColor=white) ![Tavily Search](https://img.shields.io/badge/Tavily_Search-000000?style=flat-square) |
| **Infra & DevOps** | ![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white) ![Docker Compose](https://img.shields.io/badge/Docker_Compose-2496ED?style=flat-square&logo=docker&logoColor=white) ![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white) ![AWS S3](https://img.shields.io/badge/AWS_S3-569A31?style=flat-square&logo=amazons3&logoColor=white) ![Vercel](https://img.shields.io/badge/Vercel-000000?style=flat-square&logo=vercel&logoColor=white) |

---

## 🚀 Solved Projects

### ReadWith — 독서 위치에 맞춰 등장인물 관계를 보여주는 서비스
> **Team Project / Awarded (캡스톤디자인 최우수상)** · 프론트엔드 담당

* **Problem**:
  * 인물이 많은 소설은 관계를 놓치기 쉽지만, 전체 관계도를 보여주면 스포일러가 됨
  * EPUB을 텍스트로 변환하면 위치 정보가 사라져, LLM이 뽑은 사건을 리더 화면 위치와 연결할 수 없음

* **Solution**:
  * `chapterIndex + blockIndex + offset` 형태의 locator 모델로 원문과 분석 결과의 위치를 대응시키고, 프론트에서는 같은 좌표계를 DOM 위에 다시 구현(페이지 ↔ locator 양방향 변환)
  * 사건별 관계 변화량(Delta)만 저장하고, 독자의 현재 위치 이전 사건까지만 누적(Fold)해서 그래프 생성
  * 누적 스냅샷 방식 대비 관계 item 수 약 95.9%, JSON 크기 약 94.9% 감소
  * EPUB마다 구조가 달라 정규화 파이프라인을 만들었고, Gutenberg 샘플 12종 회귀 테스트 12/12 통과
  * 그래프 갱신 시 기존 노드 위치는 유지하고 새 노드만 연결된 인물 근처에 배치

* **Tech**: `React` `Cytoscape.js` `Spring Boot` `MySQL` `AWS S3`
* **Links**: [🔗 Live Demo](https://readwith-frontend.vercel.app/) | [💻 Repo](https://github.com/Read-With)

<br>

### 사내규정 sLLM — LoRA로 학습한 HR 규정 안내 모델
> **Personal Project / SKALA sLLM 실습**

* **Problem**:
  * 가상 회사의 고유 코드 체계를 Base 모델이 모르고, 모른다고 말하지도 않음
  * 첫 SFT 모델은 점수는 올랐지만 답변 20건 중 11건에서 문장 중간에 일본어·중국어가 섞이고 없는 코드를 만들어냄
  * NVIDIA GPU가 없는 환경

* **Solution**:
  * Apple Silicon(MPS)에서 FP32 LoRA로 학습(1회 약 47분). 장치에 따라 CUDA는 QLoRA, MPS/CPU는 FP32로 나뉘도록 구성
  * 원인 가설 6개를 세우고 한 번에 하나씩 검증. 정밀도와 입력 길이는 영향이 없었고, 평가 때 쓴 `no_repeat_ngram_size` 옵션이 원인이었음
  * 평가 지표가 지어낸 답변에 안전성 만점을 주는 문제를 원문 대조로 발견해 탐지 패턴을 보강하고 진단 지표 추가
  * 종합 점수 0.19 → 0.45, 평가 20건 중 18건에서 Base보다 우세, 다국어 이탈 11건 → 0건
  * 점수가 0.75까지 나온 버전은 eval_loss가 지나치게 낮아 과적합으로 판단해 채택하지 않음
  * 남은 한계(사내 코드 정확도 0.47, unknown 질문 5건 중 2건 날조)는 RAG로 보완할 부분으로 정리

* **Tech**: `Python` `PyTorch` `Transformers` `TRL` `PEFT(LoRA)`

<br>

### 응급실 탐색 에이전트 — 주변 응급실 병상·연락처를 안내하는 LangGraph 에이전트
> **Team Project (6인) / 화면·검증 담당**

* **Problem**:
  * 모듈을 병합한 뒤 테스트 140개가 통과했지만, 오류 때문에 핵심 검색 모듈 테스트가 실행되지 않고 있었음
  * 실제 API 기준 일반 검색이 약 21초(1회 측정), 검색 한 번에 메인 모델이 5번 호출됨

* **Solution**:
  * 모듈 경계마다 최소 재현을 만들어 결함 10건을 찾고, 최종적으로 테스트 329건 전부 통과 및 실제 API 연동 확인
  * 테스트가 전부 skip되거나 수집 오류가 있으면 실패로 처리하는 검증 스크립트 작성
  * 방문 계획 저장은 사용자 승인(HITL) 후에만 가능하게 하고, 거절 0회 / 승인 1회 / 중복 승인 0회를 실제 API 환경에서 확인
  * 서버가 이미 도구 호출 순서를 정하는 구조여서, 결과에 영향이 없는 모델 호출을 건너뛰게 해 검색 한 턴의 모델 호출을 5회 → 1회로 감소
  * 호출 수가 늘면 CI가 실패하도록 예산 검사를 추가하고, 실제 API 지연·비용은 매일 측정
  * 개선 후 실제 지연 시간은 아직 충분히 쌓이지 않아 수치로 적지 않음

* **Tech**: `Python` `LangGraph` `LangChain` `Streamlit` `pytest` `GitHub Actions`

<br>

### 지역 공동물류 플랫폼 (B2G2B) — MSA 기반 분산 시스템
> **Team Project / MSA Architecture Reference**

* **Problem**:
  * 서비스를 나누면 신청-정산-활성화 흐름의 정합성을 맞추기 어려움
  * Java 서비스 사이에 Python 서비스를 넣어야 하고, 서비스마다 인증 검증이 중복됨
  * 백엔드 API는 바꿀 수 없는데, 프론트에서 도메인을 공동물류로 바꿔 보여줘야 함

* **Solution**:
  * Kafka 이벤트 기반 Choreography Saga로 신청-정산-활성화 처리
  * Spring Cloud Gateway에서 JWT를 한 번에 검증하고 내부 서비스로 신원을 전달
  * Python(FastAPI) 추천 서비스를 Eureka, Kafka, JWKS 인증에 연결. 타임아웃과 폴백을 넣어 추천이 실패해도 다른 기능이 막히지 않게 함
  * 백엔드는 그대로 두고 Vue 3 표시 계층에서 카테고리를 매핑하고, 비동기 상태 변경은 조건부 폴링으로 화면에 반영
  * 신청 기록이 남도록 `REQUIRES_NEW`로 PENDING 저장을 먼저 커밋
  * 보상 트랜잭션, 멱등성, DLQ는 아직 없어 문서에 한계로 기록

* **Tech**: `Java 21` `Spring Boot 3` `Spring Cloud` `Apache Kafka` `FastAPI` `Vue 3` `MariaDB` `Docker Compose`

<br>

### SkinAgent — 스킨케어 성분 충돌 분석 및 루틴 안내 에이전트
> **Personal Project / AI Agent**

* **Problem**:
  * 화장품을 같이 쓸 때 성분끼리 충돌하는지(비타민C, 레티놀 등) 일일이 확인하기 어려움
  * 세션이 끝나면 사용자의 피부 고민과 기피 성분이 사라짐
  * 광민감성 같은 성분 특성에 따른 아침/저녁 구분 안내가 없음

* **Solution**:
  * 대화 맥락에 따라 LLM이 성분 조회, 충돌 분석 도구의 호출 여부와 순서를 결정
  * 세션 내 대화는 LangGraph로, 사용자 프로필은 SQLite에 따로 저장해 세션이 끝나도 유지
  * 비의료 질문 차단, 개인정보 마스킹, 출력에 기피 성분이 있으면 다시 생성하는 가드레일
  * Pydantic 스키마로 위험도(Safe/Caution/Danger)와 시간대별 루틴을 만들어 Streamlit 카드로 표시

* **Tech**: `Python 3` `LangGraph` `Pydantic` `SQLite` `Streamlit`

<br>

### Medical Big Data Analytics — 임상 데이터 기반 예측 분석
> **Data Analysis / Awarded (경진대회 장려상)**

* **Problem**:
  * 임상 데이터의 결측치, 이상치, 클래스 불균형으로 모델 예측이 한쪽으로 치우침
  * 수치형 검사 지표와 범주형 진단 코드처럼 형태가 다른 데이터를 함께 다뤄야 함

* **Solution**:
  * 결측치 대체와 이상치 필터링 파이프라인, 임상 지식 기반 파생 변수 추출
  * 클래스 가중치 조정과 LightGBM/XGBoost로 소수 위험군 분류 성능 개선
  * Seaborn으로 통계 리포트를 만들고 Feature Importance로 주요 위험 인자 확인

* **Tech**: `Python` `Pandas` `Scikit-Learn` `LightGBM` `Seaborn` `Matplotlib`

---

## 🔬 More Experiments

* **한국어 감정 분류 토크나이저 직접 구현**: 형태소 분석기(Okt)의 JVM 의존성 때문에 순수 Python으로 빈도·BPE·n-gram 토크나이저를 구현. BPE에서 [UNK] 비율이 높은 원인을 추적해, 학습 때 정한 병합 순서를 저장하지 않아 추론에서 재현되지 않는 문제를 찾아 수정
* **리뷰 생성 · OCR 보정**: 이미지 전처리와 LLM 후처리로 OCR 오인식을 줄이고 리뷰 초안을 생성
* **내자리 어딨냐** (설계 단계): 같은 주차 자리의 동시 예약을 DB의 Partial Unique Index로 막도록 설계
---

© 2026 Yelli915. All rights reserved.
