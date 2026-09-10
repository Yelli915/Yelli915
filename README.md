# 🟢 Status: Active | Yelli915

> 특정 스택에 갇히지 않고, **비즈니스와 사용자 경험의 문제를 데이터·AI 기술로 구조화하여 해결하는 엔지니어**입니다.

[![Naver Blog](https://img.shields.io/badge/Naver_Blog-yelli915-03CF5D?style=for-the-badge&logo=naver&logoColor=white)](https://blog.naver.com/yeri8791)
[![Tistory](https://img.shields.io/badge/Tistory-yelli915-EA5328?style=for-the-badge&logo=tistory&logoColor=white)](https://yelli915.tistory.com/)

---

## 💡 Engineering Focus & Problem Solving

* **도메인 문제 정의**: 복잡한 사용자 Pain Point를 직관적인 인터랙션과 시스템으로 단순화합니다.
* **AI & 데이터 기반 해결**: 정형/비정형 데이터를 정제하고, LLM과 프롬프트 엔지니어링을 결합해 실질적인 자동화 가치를 만듭니다.
* **확장 가능한 엔지니어링**: UI 시각화부터 백엔드 데이터 파이프라인까지, 문제가 요구하는 최선의 기술 체계를 구축합니다.

---

## 🏆 Verified Impact & Awards

* **🥇 최우수상 수상** — **LLM 기반 독서 지원 시스템**
  * 텍스트 정보의 난해함이라는 문제를 LLM 관계 추출 및 Cytoscape.js 시각화 엔진으로 해결
* **🏅 장려상 수상** — **의료 빅데이터 분석 프로젝트**
  * 대규모 의료 데이터의 노이즈를 정제하고 인사이트 패턴을 도출하는 분석 알고리즘 구현

---

## ⚙️ Engineering Toolset

| Category | Problem Solving Tools |
| :--- | :--- |
| **Interface & Graph** | ![React](https://img.shields.io/badge/React-61DAFB?style=flat-square&logo=react&logoColor=black) ![Next.js](https://img.shields.io/badge/Next.js-000000?style=flat-square&logo=nextdotjs&logoColor=white) ![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black) ![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-06B6D4?style=flat-square&logo=tailwindcss&logoColor=white) |
| **Data & Architecture** | ![Node.js](https://img.shields.io/badge/Node.js-339933?style=flat-square&logo=nodedotjs&logoColor=white) ![Supabase](https://img.shields.io/badge/Supabase-3ECF8E?style=flat-square&logo=supabase&logoColor=white) ![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white) |
| **AI Integration** | ![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white) ![Google Gemini](https://img.shields.io/badge/Gemini_API-8E75B2?style=flat-square&logo=googlegemini&logoColor=white) |

---

## 🚀 Solved Projects

### 📖 ReadWith — 독서 진행 위치 기반 등장인물 관계 시각화 시스템
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

### ✍️ Auto Review Generator — LLM 기반 자동 리뷰 생성 서비스
> **Personal Project**

* **Problem**: 서비스 이용 후 후기 작성 시 발생하는 사용자 피로도 및 작성 진입장벽
* **Solution**: 파편화된 핵심 키워드 조합만으로 정교한 리뷰 텍스트를 자동 합성해주는 LLM 파이프라인 설계
* **Tech**: `React / Next.js` `Gemini API` `Tailwind CSS` `Prompt Engineering`
* **Links**: [🔗 Live Demo](https://autoreviewer-mauve.vercel.app/) | [💻 Repo](https://github.com/Yelli915/auto-review-generator)

<br>

### 📊 Medical Big Data Analytics Project
> **Data Analysis / Awarded (장려상)**

* **Problem**: 의료 데이터 내 대규모 노이즈와 비정형 패턴의 분석 난제
* **Solution**: 데이터 정제 파이프라인 구축 및 통계적 시각화를 통한 인사이트 추출
* **Tech**: `Python` `Data Analysis` `Visualization`

---

© 2026 Yelli915. All rights reserved.
