# 🟢 Status: Active | Yelli915

> 특정 스택에 갇히지 않고, **비즈니스와 사용자 경험의 문제를 데이터·AI 기술로 구조화하여 해결하는 엔지니어**입니다.

[![Naver Blog](https://img.shields.io/badge/Naver_Blog-yelli915-03CF5D?style=for-the-badge&logo=naver&logoColor=white)](https://blog.naver.com/yeri8791)
[![Tistory](https://img.shields.io/badge/Tistory-yelli915-EA5328?style=for-the-badge&logo=tistory&logoColor=white)](https://yelli915.tistory.com/)

---

## 💡 Engineering Focus & Problem Solving

* **도메인 분해 & MSA 설계**: 단일 장애점을 방지하고 서비스별 독립적인 확장성을 확보하기 위해, 도메인 중심의 마이크로서비스(Java 21 / Spring Boot 3, FastAPI)와 서비스 디스커버리 및 게이트웨이 생태계를 구축합니다.
* **이벤트 기반 분산 트랜잭션 (Saga Pattern)**: 서비스 간 강결합을 해소하기 위해 Apache Kafka 기반 비동기 이벤트 체이닝을 구축하고, 트랜잭션 격리를 통해 분산 환경에서도 비즈니스 상태 전이의 최종 정합성을 보장합니다.
* **AI 오케스트레이션 & 최적화**: 단순 텍스트 생성을 넘어 LLM의 Tool Calling, 다단계 가드레일, 정규화 좌표계(Locator) 및 Delta 누적 연산 등을 결합해 실질적인 성능 및 데이터 효율을 창출합니다.

---

## 🏆 Verified Impact & Awards

* **🥇 최우수상 수상** — **ReadWith (캡스톤디자인)**
  * EPUB 문단 정규화 좌표계 구축 및 관계 Delta 기반 시점별 그래프 복원으로 독서 위치 연동 스포일러 방지 달성
* **🏅 장려상 수상** — **의료 빅데이터 분석 프로젝트**
  * 대규모 의료 데이터의 결측치·노이즈를 정제하고 예측 모델링 및 통계적 시각화를 통한 인사이트 추출

---

## ⚙️ Engineering Toolset

| Category | Problem Solving Tools |
| :--- | :--- |
| **Frontend & Visualization** | ![React](https://img.shields.io/badge/React-61DAFB?style=flat-square&logo=react&logoColor=black) ![Next.js](https://img.shields.io/badge/Next.js-000000?style=flat-square&logo=nextdotjs&logoColor=white) ![Vue.js](https://img.shields.io/badge/Vue.js_3-4FC08D?style=flat-square&logo=vuedotjs&logoColor=white) ![Streamlit](https://img.shields.io/badge/Streamlit-FF4B4B?style=flat-square&logo=streamlit&logoColor=white) ![Cytoscape.js](https://img.shields.io/badge/Cytoscape.js-EA5328?style=flat-square) ![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-06B6D4?style=flat-square&logo=tailwindcss&logoColor=white) |
| **Backend & Architecture** | ![Java](https://img.shields.io/badge/Java_21-ED8B00?style=flat-square&logo=openjdk&logoColor=white) ![Spring Boot](https://img.shields.io/badge/Spring_Boot_3-6DB33F?style=flat-square&logo=springboot&logoColor=white) ![Spring Cloud](https://img.shields.io/badge/Spring_Cloud-6DB33F?style=flat-square&logo=spring&logoColor=white) ![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white) |
| **Message & Database** | ![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white) ![MariaDB](https://img.shields.io/badge/MariaDB-003545?style=flat-square&logo=mariadb&logoColor=white) ![SQLite](https://img.shields.io/badge/SQLite-003B57?style=flat-square&logo=sqlite&logoColor=white) |
| **AI & Orchestration** | ![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white) ![Google Gemini](https://img.shields.io/badge/Gemini_API-8E75B2?style=flat-square&logo=googlegemini&logoColor=white) ![LangGraph/Agent](https://img.shields.io/badge/LLM_Agent-FF6F00?style=flat-square) ![Pydantic](https://img.shields.io/badge/Pydantic-E92063?style=flat-square&logo=pydantic&logoColor=white) ![Tavily Search](https://img.shields.io/badge/Tavily_Search-000000?style=flat-square) |
| **Infra & DevOps** | ![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white) ![Docker Compose](https://img.shields.io/badge/Docker_Compose-2496ED?style=flat-square&logo=docker&logoColor=white) ![AWS S3](https://img.shields.io/badge/AWS_S3-569A31?style=flat-square&logo=amazons3&logoColor=white) ![Vercel](https://img.shields.io/badge/Vercel-000000?style=flat-square&logo=vercel&logoColor=white) |

---

## 🚀 Solved Projects

### ReadWith — 독서 진행 위치 기반 등장인물 관계 시각화 시스템
> **Team Project / Awarded (캡스톤디자인 최우수상)**

* **Problem**: 방대한 소설 텍스트의 복잡한 인물 관계 파악 한계, 전체 관계도 제공으로 인한 스포일러 노출, EPUB 리더 화면과 AI 분석 텍스트 간의 위치 단절
* **Solution**: 
  * 문단 기반 `locator`와 canonical `txtOffset`을 양방향 매핑하는 좌표계를 구축하여 뷰어 화면 위치와 AI 분석 이벤트 구간을 1:1 정합
  * 사건별 관계 변화량(Delta)만 DB에 적재한 뒤 독자의 현재 독서 위치 이전 사건까지만 동적 누적(Fold) 연산하여 **스포일러 차단 그래프** 구현
  * 누적 스냅샷 방식 대비 관계 item 수 약 95.9%, JSON 페이로드 크기 약 94.9% 절감 및 S3 Staging 기반 비동기 적재 파이프라인 구축
  * `Cytoscape.js` 엔진을 활용해 독서 진도와 실시간 연동되는 동적 인터랙티브 네트워크 그래프 UI 구현
* **Tech**: `React` `Cytoscape.js` `Spring Boot` `MySQL` `AWS S3`
* **Links**: [🔗 Live Demo](https://readwith-frontend.vercel.app/) | [💻 Repo](https://github.com/Read-With)

<br>

### 지역 공동물류 플랫폼 (B2G2B) — MSA 기반 분산 시스템
> **Team Project / MSA Architecture Reference**

* **Problem**: 
  * 모놀리식 구조의 결합도 문제 및 마이크로서비스 분해 시 발생하는 분산 트랜잭션 정합성(신청-정산-활성화) 유지 난제
  * 이종 런타임(Java/Python) 간 통합 및 서비스별 인증 검증 중복 발생
  * 백엔드 API 계약 변경 없이 프론트엔드 관점에서 도메인을 유연하게 재정의해야 하는 요구사항

* **Solution**: 
  * **도메인 분해 & 분산 트랜잭션 (Saga)**: Java 21 / Spring Boot 3 기반 도메인 분해 및 Apache Kafka 이벤트 체이닝을 활용한 Choreography Saga로 서비스 간 결합도 최소화 및 정합성 보장
  * **Token Relay 인증 위임**: Spring Cloud Gateway에서 JWT를 일괄 검증하고 내부 서비스로 신원을 릴레이하여 인증 로직 중복 제거
  * **폴리글랏(Polyglot) 추천 서비스 통합**: Python(FastAPI) 추천 서비스를 공통 인증(JWKS) 및 메시징(Kafka) 생태계에 유연하게 결합
  * **도메인 리라벨링 & 실행 환경 구성**: 백엔드 계약을 유지한 채 Vue 3 표시 계층에서 공동물류 도메인으로 매핑하는 패턴 적용 및 Docker Compose 기반 통합 환경 구성

* **Tech**: `Java 21` `Spring Boot 3` `Spring Cloud` `Apache Kafka` `FastAPI` `Vue 3` `MariaDB` `Docker Compose`

<br>

### SkinAgent — AI 기반 맞춤형 스킨케어 성분 충돌 분석 및 루틴 케어 에이전트
> **Team Project (6인) / AI Agent Architecture Reference**

* **Problem**: 
  * 화장품 병용 시 발생하는 성분 간 충돌 위험(비타민C, 레티놀 등)의 수동 대조 한계
  * 단일 세션 조회 중심 구조로 인한 사용자 피부 고민 및 기피 성분 이력 휘발
  * 성분 특성(광민감성 등)을 고려한 아침/저녁 분리 사용 가이드 부재

* **Solution**: 
  * **자율 Tool Calling 오케스트레이션**: LLM이 대화 맥락에 따라 성분 조회 및 충돌 분석 도구의 호출 여부와 순서를 동적으로 결정하는 에이전트 파이프라인 설계
  * **이중 메모리 아키텍처 (Long/Short-term)**: LangGraph 기반 세션 내 단기 문맥 유지와 SQLite 파일 기반 장기 프로필 저장소를 분리하여 세션 리셋 후에도 개인화 데이터 유지
  * **방어적 다단계 가드레일**: 비의료적 질의 차단, 개인정보 마스킹, 출력 후 기피 성분 포함 여부 2차 감사(자가 교정 루틴 재생성)로 안전성 확보
  * **Pydantic 기반 구조화된 출력**: 위험도(Safe/Caution/Danger) 판정 및 시간대별 분리 루틴을 정형 스키마로 정의하여 Streamlit 카드 UI로 렌더링

* **Tech**: `Python 3` `LLM Agent` `Tool Calling` `LangGraph` `Pydantic` `SQLite` `Streamlit`

<br>


### 📊 Medical Big Data Analytics Project
> **Data Analysis / Awarded (장려상)**

* **Problem**: 의료 데이터 내 대규모 결측치, 노이즈와 비정형 패턴 분석의 한계
* **Solution**: 결측치 정제 파이프라인 구축 및 탐색적 데이터 분석(EDA), 통계적 시각화를 통한 인사이트 추출
* **Tech**: `Python` `Data Analysis` `Visualization` `Scikit-Learn`

---

© 2026 Yelli915. All rights reserved.
