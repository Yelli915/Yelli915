# 🟢 Status: Active | Yelli915

> 결과가 잘 나왔을 때 "진짜 잘 된 건가?"를 한 번 더 확인하는 AI 엔지니어입니다.

[![Naver Blog](https://img.shields.io/badge/Naver_Blog-yelli915-03CF5D?style=for-the-badge&logo=naver&logoColor=white)](https://blog.naver.com/yeri8791)
[![Tistory](https://img.shields.io/badge/Tistory-yelli915-EA5328?style=for-the-badge&logo=tistory&logoColor=white)](https://yelli915.tistory.com/)

---

## 💡 Engineering Focus

* **원인을 나눠서 찾기**: 모델이 이상하게 동작하면 재학습부터 하지 않고, 학습 변수와 평가 변수를 나눠 하나씩 바꿉니다. sLLM에서 답변이 깨지던 원인이 학습이 아니라 평가 옵션이었다는 걸 이렇게 찾았습니다.
* **LLM을 쓰지 않을 곳 정하기**: 응급실 에이전트에서 정해진 검색 순서는 코드로, 문장 작성만 모델에 맡겨 모델 호출을 5회 → 1회로 줄였습니다. 안전 규칙도 프롬프트가 아니라 코드 경로로 막습니다.
* **원본과의 대응 관계 유지하기**: ReadWith에서 EPUB을 LLM 입력으로 바꿀 때 사라지는 위치 정보를 locator 좌표계로 보존했습니다.
* **한계 기록하기**: 측정하지 못한 항목과 남은 문제는 수치와 함께 문서에 남깁니다.

---

## 🏆 Awards

* **🥇 최우수상** — ReadWith (캡스톤디자인)
* **🏅 장려상** — 의료 빅데이터 분석 경진대회

---

## ⚙️ Tech Stack

| Category | Tools |
| :--- | :--- |
| **AI & Agent** | ![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white) ![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white) ![HuggingFace](https://img.shields.io/badge/Transformers_·_PEFT_·_TRL-FFD21E?style=flat-square&logo=huggingface&logoColor=black) ![LangGraph](https://img.shields.io/badge/LangGraph_·_LangChain-FF6F00?style=flat-square) ![Gemini](https://img.shields.io/badge/Gemini_API-8E75B2?style=flat-square&logo=googlegemini&logoColor=white) ![Pydantic](https://img.shields.io/badge/Pydantic-E92063?style=flat-square&logo=pydantic&logoColor=white) |
| **Backend** | ![Java](https://img.shields.io/badge/Java_21-ED8B00?style=flat-square&logo=openjdk&logoColor=white) ![Spring Boot](https://img.shields.io/badge/Spring_Boot_3-6DB33F?style=flat-square&logo=springboot&logoColor=white) ![Spring Cloud](https://img.shields.io/badge/Spring_Cloud-6DB33F?style=flat-square&logo=spring&logoColor=white) ![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white) ![Kafka](https://img.shields.io/badge/Kafka-231F20?style=flat-square&logo=apachekafka&logoColor=white) ![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white) ![MariaDB](https://img.shields.io/badge/MariaDB-003545?style=flat-square&logo=mariadb&logoColor=white) |
| **Frontend** | ![React](https://img.shields.io/badge/React-61DAFB?style=flat-square&logo=react&logoColor=black) ![Vue.js](https://img.shields.io/badge/Vue.js_3-4FC08D?style=flat-square&logo=vuedotjs&logoColor=white) ![Cytoscape.js](https://img.shields.io/badge/Cytoscape.js-EA5328?style=flat-square) ![Streamlit](https://img.shields.io/badge/Streamlit-FF4B4B?style=flat-square&logo=streamlit&logoColor=white) |
| **Infra** | ![Docker](https://img.shields.io/badge/Docker_Compose-2496ED?style=flat-square&logo=docker&logoColor=white) ![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white) ![AWS S3](https://img.shields.io/badge/AWS_S3-569A31?style=flat-square&logo=amazons3&logoColor=white) ![Vercel](https://img.shields.io/badge/Vercel-000000?style=flat-square&logo=vercel&logoColor=white) |

---

## 🚀 Projects

### ReadWith — 독서 위치에 맞춰 등장인물 관계를 보여주는 서비스
> **Team Project · 캡스톤디자인 최우수상** · 프론트엔드 담당

* **Problem**
  * 전체 관계도를 보여주면 스포일러가 되고, EPUB을 텍스트로 바꾸면 위치 정보가 사라져 LLM이 뽑은 사건을 리더 화면과 연결할 수 없음
* **Solution**
  * `chapterIndex + blockIndex + offset` locator로 원문과 분석 결과의 위치를 대응시키고, 프론트에서 같은 좌표계를 DOM 위에 구현(페이지 ↔ locator 양방향 변환)
  * 사건별 관계 변화량(Delta)만 저장하고 현재 독서 위치까지만 누적해 그래프 생성 → 누적 스냅샷 방식 대비 관계 item 약 95.9%, JSON 크기 약 94.9% 감소
  * 구조가 제각각인 EPUB 정규화 파이프라인, Gutenberg 샘플 12종 회귀 테스트 12/12 통과
* **Tech**: `React` `Cytoscape.js` `Spring Boot` `MySQL` `AWS S3`
* **Links**: [🔗 Live Demo](https://readwith-frontend.vercel.app/) | [💻 Repo](https://github.com/Read-With)

<br>

### ER Finder — 응급실 병상을 API 근거로 안내하는 LangGraph 에이전트
> **Team Project (6인) → v2 통합·재설계 단독** · 1차: 메모리 모듈(세션·방문 계획 저장소)

* **Problem**
  * 위급한 사용자가 LLM 응답을 기다리거나, LLM이 없는 병원·병상을 말할 수 있음
  * 위치·증상 같은 민감 정보가 동의 없이 저장될 수 있음
  * 검색 한 번에 메인 모델 5회 호출, 실제 API 기준 약 21초(1회 측정)
* **Solution**
  * 따로 만든 메모리·검색·가드레일·의료 API·화면 모듈을 하나의 LangGraph 에이전트로 통합
  * 위급한 입력은 모델 호출 전에 119 안내로 넘김. LLM 분류기는 위급도를 올리기만 하고 낮출 수는 없게 함
  * 모델이 낸 수치는 쓰지 않고 API 조회 근거로 답변을 다시 조립 → 최종 답변의 병원·병상 정보는 API 값에서만 나옴
  * 방문 계획은 사용자 승인 후 1회만 저장(interrupt/resume), PII 마스킹
  * 도구 순서를 서버가 정해 모델 호출 5 → 1회, P50 약 21초 → 5~8초(재측정 6~10초). 같은 시기 모델 교체(OpenAI → Gemini)가 섞여 효과는 분리하지 못함
  * 합성 골든셋 75건 기준 위급도 규칙 정확도 85.9% → 96.9%, 위급 재현율 100%(놓친 사례로 규칙을 보강한 결과라 일반화 성능은 아님)
  * 오프라인 테스트 426개(ruff·mypy --strict), 실제 API 계약 매일 점검 CI. 임상 적절성·추천 정확도는 미측정
* **Tech**: `Python` `LangGraph` `Gemini API` `Streamlit` `pytest` `GitHub Actions`

<br>

### 사내규정 sLLM — LoRA로 학습한 HR 규정 안내 모델
> **Personal Project · SKALA sLLM 실습**

* **Problem**
  * Base 모델이 가상 회사의 고유 코드 체계를 모르고, 모른다고 말하지도 않음
  * 첫 SFT 모델은 점수는 올랐지만 20건 중 11건이 문장 도중 일본어·중국어로 넘어가고 없는 코드를 만들어냄
* **Solution**
  * GPU 없는 환경에서 MPS FP32 LoRA로 학습(1회 약 47분), 장치에 따라 CUDA는 QLoRA로 분기
  * 원인 가설 6개를 한 번에 하나씩 검증 → 정밀도·입력 길이는 영향 없음, 평가 옵션 `no_repeat_ngram_size`가 원인
  * 지어낸 답변에 안전성 만점을 주던 지표를 원문 대조로 발견해 탐지 패턴 보강, 진단 지표 추가
  * 종합 점수 0.19 → 0.45, 20건 중 18건 Base 대비 우세, 다국어 이탈 11건 → 0건
  * 점수 0.75 버전은 규정에 없는 질문의 날조가 2건 → 3건으로 늘어 기각
  * 남은 한계(코드 정확도 0.47, 날조 2/5)는 RAG로 보완할 부분으로 정리
* **Tech**: `Python` `PyTorch` `Transformers` `TRL` `PEFT(LoRA)`

<br>

### LocalLink — 지역 공동물류 플랫폼 (B2G2B, MSA)
> **SKALA 팀 프로젝트 → 개인 확장** · 팀: 추천 서비스·신청 상태 폴링 / 개인: 정산 실패·중복 이벤트 처리, 내부 API 보호

* **Problem**
  * 정산 타임아웃을 실패로 처리하면 "정산됨 + 참여 실패" 불일치가 생김
  * 같은 이벤트를 다시 받으면 참여 건수가 중복 증가
  * 서비스 포트로 직접 요청하면 `X-User-Id` 위조 가능
* **Solution**
  * 신청은 PENDING으로 응답하고 `settlement.completed` 이벤트 수신 후 ACTIVE로 변경(Kafka)
  * 확실한 실패는 FAILED(재신청 시 복구), 타임아웃·5xx는 PENDING 유지 후 늦게 온 이벤트로 복구
  * `UPDATE ... WHERE status = ...`로 상태가 실제로 바뀐 경우만 후속 처리 → 같은 이벤트 동시 8건에도 부수효과 1회
  * 내부 API 토큰 검사·포트 비공개·헤더 위조 차단, 추천 장애 시 인기순·빈 목록으로 대체 응답
  * 한계: DB 커밋과 Kafka 발행 분리(→ Outbox), 재시도·DLQ 없음, 서비스 간 DB 공유
* **Tech**: `Java 21` `Spring Boot 3` `Spring Cloud` `Kafka` `FastAPI` `Vue 3` `MariaDB` `Docker Compose`

<br>

### SkinAgent — 스킨케어 성분 충돌 분석 에이전트
> **Personal Project**

* 성분 조회·충돌 분석 도구를 LLM이 대화 맥락에 따라 호출하고, 사용자 프로필은 SQLite에 저장해 세션이 끝나도 유지
* 비의료 질문 차단, 개인정보 마스킹, 출력에 기피 성분이 있으면 다시 생성하는 가드레일
* **Tech**: `Python` `LangGraph` `Pydantic` `SQLite` `Streamlit`

---

## 🔬 More

* **의료 빅데이터 분석 (장려상)**: 임상 데이터 결측치·이상치 정제와 클래스 가중치 조정, LightGBM/XGBoost로 소수 위험군 분류
* **한국어 감정 분류 토크나이저**: 순수 Python으로 BPE 등을 구현하고, [UNK] 비율이 높던 원인(병합 순서 미저장)을 찾아 수정
* **리뷰 생성 · OCR 보정**: 이미지 전처리와 LLM 후처리로 OCR 오인식 보정
* **내자리 어딨냐** (설계 단계): 동시 예약을 Partial Unique Index로 막도록 설계

---

© 2026 Yelli915. All rights reserved.
