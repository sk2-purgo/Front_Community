![header](https://capsule-render.vercel.app/api?type=waving&color=gradient&height=192&section=header&text=COMMUNITY%20FRONTEND&fontSize=65&animation=fadeIn&fontColor=FFF)

<div align="center">

![React](https://img.shields.io/badge/React-18-blue?logo=react)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?logo=typescript&logoColor=white)
![Redux](https://img.shields.io/badge/Redux-764ABC?logo=redux&logoColor=white)
![React Router](https://img.shields.io/badge/React--Router-D0021B?logo=react-router&logoColor=white)
![Styled Components](https://img.shields.io/badge/styled--components-DB7093?logo=styled-components&logoColor=white)
![Framer Motion](https://img.shields.io/badge/Framer--Motion-EF0179?logo=framer&logoColor=white)
![Axios](https://img.shields.io/badge/Axios-5A29E4?logo=axios&logoColor=white)
![react-fullpage](https://img.shields.io/badge/react--fullpage-1E1E1E?logo=react&logoColor=white)

</div>



패키지 설치 방법
```
npm install
2. npm install @fullpage/react-fullpage
3. npm install recharts
```

---

# 🚀 Purgo: 비속어 정제 체험 서비스 소개

요즘 온라인 커뮤니케이션에서 **비속어 정제**는 점점 더 중요한 이슈가 되고 있습니다. **Purgo**는 이 문제를 직접 다루는 웹 기반 체험 서비스로, 사용자가 직접 입력한 문장에서 **비속어를 감지하고 정제하는 기능**을 제공합니다.

---

# 🔧 **기술 스택 요약**

- **프레임워크/언어**: React 18, TypeScript
- **상태 관리**: Redux, Redux-Actions, React-Redux, Redux Devtools
- **라우팅**: React Router DOM
- **스타일링**: styled-components, styled-reset
- **UI 애니메이션/효과**: framer-motion, AOS, react-countup, react-curved-text, typewriter-effect
- **아이콘/폰트**: FontAwesome (`@fortawesome`), Lucide-React
- **날짜/시간 처리**: date-fns, react-datepicker
- **입력 처리**: react-hook-form, react-daum-postcode, react-modal
- **리치 콘텐츠 처리**: react-markdown, remark-gfm, react-syntax-highlighter
- **차트 시각화**: recharts
- **HTTP 통신**: axios
- **스크롤 인터랙션**: react-fullpage, @fullpage/react-fullpage
- **이메일 발송**: emailjs-com, @emailjs/browser
- **기타**: multer (파일 업로드용), global

---

# React 컴포넌트 아키텍처: Container-Presentational 패턴
```
MyPage/
├── Container.tsx  // 🧠 비즈니스 로직 + 상태 관리
├── Page.tsx          // 🎨 순수 UI 렌더링
└── style.ts           // 💅 스타일 컴포넌트
```
## 🧠 Container 컴포넌트:

Container는 "두뇌" 역할을 담당합니다. 데이터를 가져오고, 상태를 관리하고, 이벤트를 처리함.

**상태 관리, API 호출, 에러 처리, 네비게이션, UI 컴포넌트로** **Props 전달**

## 🎨 Presentational 컴포넌트: MyPage.tsx

UI 컴포넌트는 "얼굴" 역할을 담당합니다. 받은 데이터를 예쁘게 화면에 보여주기만 함.

## 💅 스타일 컴포넌트: style.ts

스타일은 완전히 분리되어 재사용 가능한 형태로 관리됨.

---

# ✅ 페이지의 핵심 기능 요약

## 메인 소개 페이지

### 1. **메인 배너에 실시간 AI 정제 확인 가능**

- `MainBanner` 내부에 `AIMessagePurifier` 컴포넌트 포함
    
    → 사용자 입장에서 **AI가 어떻게 비속어를 감지하고 정제하는지 한 눈에 볼 수 있음**

### 2. **서비스 소개 및 API 키 안내 섹션**

- `MiddleSection`은 두 개의 클릭 가능한 카드로 구성:
    - **서비스 소개 영역** (`/detail`로 이동): 서비스 특징 설명용
    - **API 키 사용법 영역** (`/docs/start`로 이동): 개발자를 위한 문서 링크 제공
- `FileIcon`, `LockIcon`을 통해 직관적 아이콘 UI 제공
- 마우스 hover 시 설명 문구 등장 (인터랙션 강조)

### 3. **API Key 발급 팝업 기능**

- 상단 헤더(`Header`)에서 "API 키 신청"을 클릭하면 `ApiKeyPopup`이 열림
- `useState`로 팝업의 상태 제어 (`isPopupOpen`)
- 사용자 인증 및 체험 유도를 위한 **상호작용 요소 강화**

### 5. **모듈화된 구조로 재사용성과 유지보수 용이성 확보**

- `Header`, `Footer`, `ApiKeyPopup`, `AIMessagePurifier` 등 기능별 분리
- 스타일은 `S.` 접두어를 통해 `style.ts` 모듈로 통합 관리

## 특징 소개 페이지

### 1. **풀페이지 스크롤 랜딩 페이지**

- `ReactFullpage`를 사용한 섹션별 스크롤 내비게이션
- 4개 섹션으로 구성 (소개, 기능 시연, 성능 분석, 추가 컨테이너)

### 2. **인터랙티브 물방울(Drop) UI**

- **물방울 모양 컴포넌트**들이 다양한 플랫폼을 표현
- 마우스 호버 시 **확장 애니메이션**과 **배경색 변화**
- 3가지 purgo 서비스가 적용된 3가지 플랫폼 확인:
    - **실시간 채팅** (내부 챗 시스템)
    - **게시판** (내부 포스트 시스템)
    - **디스코드** (외부 플랫폼)

### 3. **AI 성능 시각화**

- **실시간 비속어 탐지 카운터** (CountUp 애니메이션)
- **성능 지표 막대 그래프**: 정확도, 정밀도, 재현율, F1-score
- **비속어 사용 빈도 원형 차트** (마스킹 처리된 단어들)
- **3D 회전 효과**가 적용된 인터랙티브 차트

### 4. **동적 애니메이션 시스템**

- **섹션 활성화 감지**에 따른 자동 애니메이션 트리거
- **물방울 확장 효과** (마우스 위치 기반 중심점 계산)
- **페이드 인/아웃**, **블러 효과**, **스케일 변환** 등 복합 애니메이션

### 5. **API 연동 데이터**

- 실시간 비속어 탐지 총계 조회
- 오늘 가장 많이 사용된 비속어 순위 (마스킹 처리)
- 성능 지표 데이터 시각화

## 문서 페이지 특징

### **1. `MarkdownRenderer` 컴포넌트**

- 역할: 마크다운 텍스트를 HTML로 변환 및 렌더링.
- `react-markdown`과 `remark-gfm`을 사용해 GitHub 스타일의 마크다운을 지원.
- `code` 블록은 일반 인라인 코드와 블록 코드로 구분해서 처리.
- 블록 코드(`\n` 포함)는 `CodeBlock`으로 넘기고, 복사 버튼 포함한 UI 제공.

### 2. **`CodeBlock` 컴포넌트**

- 코드 블록에 복사 버튼(`CopyButton`) 포함.
- `styled-components`로 코드 박스 스타일 적용 (배경, 폰트 등).
- 복사 기능을 통해 사용자 편의 제공.


# 🧼 Purgo: AI Profanity Filtering Web App

Purgo는 사용자 게시글 및 댓글의 욕설을 감지하고 정제된 언어로 대체해주는 웹 애플리케이션입니다.  
해당 프로젝트는 오픈소스이며 GNU GPL v3 라이선스를 따릅니다.

## 🧾 License

This project is licensed under the **GNU General Public License v3.0**.

- 자유롭게 소스코드를 사용할 수 있으며, 수정 및 배포도 가능합니다.
- Purgo는 수익을 창출하지 않는 비영리 목적의 오픈소스 프로젝트입니다.
- 단, 이 소스를 이용한 파생 프로젝트도 **동일한 GPLv3 조건**을 따라야 합니다.
- 자세한 내용은 [LICENSE](./LICENSE) 파일을 참고하세요.

⚠️ 이 프로젝트는 [fullPage.js](https://alvarotrigo.com/fullPage/)를 **GPLv3 라이선스 하에서 사용**하고 있습니다.
