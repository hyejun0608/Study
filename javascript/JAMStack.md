# JAM Stack

**J**avascript, **A**pi, **M**arkup Stack

`Javascript`, `Api`, `Markup`으로 이루어진 웹의 구성

SPA 비슷하지만 다름

### SPA(Single Page Application)와 CSR(Client Side Rendering)

웹은 `Static HTML`와 `CSS`를 네트워크로 전달 받아서 화면에 보여줌

서버가 **동적**으로 HTML을 생성할 수 있게 되면서 **Server Side Rendering(SSR)** 개념이 등장

**사용자의 요청**에 따라 HTML을 만들면서 전달하고, 화면을 보여줄 수 있게 됨

SSR만으로 더 많은 HTML의 조작이 힘들어짐

→ Javascript, jQuery가 중요한 역할

1. Jacascript로 화면을 조작할 일이 많이 생김
2. Javascript와 브라우저 성능이 더욱 발전
3. Angular, React, Vue와 같이 DOM을 쉽게 조작하게 도와주는 라이브러리 & 웹 프레임 워크 등장

⇒ **Client Side Rendering (CSR)** 개념 등장!

사용자의 환경이 더욱 발전 → **서버** 상에서 HTML을 만들어 전달 X → **클라이언트** 상에서 HTML을 만듦 O

⇒ **서버 비용**과 **렌더링 속도**에서 훨씬 유리한 환경이 됨

페이지를 이동할 때마다 HTML을 새로 받아서 그리는 것 < 필요한 데이터만을 받아 JS로 화면을 그리는 것

`정보가 없는 HTML`, `매우 큰 Javascript`, `분리된 환경의 API`으로 이루어진
**Single Page Application (SPA)**환경 등장

### SPA의 단점 2가지

사용자가 첫 의미있는 페이지(First meaningful paint)를 볼때 까지

1. SSR에 비해 오래 걸림
2. 검색 엔진이 이해할 수 있던 HMLT이 사라짐 & Javascrip만 존재
⇒ **검색 엔진 최적화** **Search Engine Optimization (SEO)**를 맞추기 어려움

하지만 Javascript로 조작하는 환경 👍, First meaningful paint와 SEO가 중요

SSR + CSR = Javascript에서 사용하는 환경을 그대로 이용한 Server
`Angular Universal`, `NextJS`, `NuxtJs` 등장

첫 페이지 → SSR 형태로 HTML을 만들어 보여줌

이후 모든 화면 조작 & Rendering (CSR)을 Javascript가 처리

⇒ 하이브리드 형태로 발전

First meaningful paint의 속도를 높힘, 검색봇이 HTML을 크로링 → SEO 대응

### JAM Stack

React(CSR), Next.js(SSR)같이 특정 기술로 구성된 형태 X

**웹 사이트**를 어떻게 **구성**할 것인지의 **관점**

1. **Javascript**
→ Client의 모든 처리는 Javascript에게 맞김
2. **Api**
→ 모든 기능 및 비지니스 로직은 재사용 가능한 API로 추상화
3. **Markup ⭐️**
→ SSG(Static Site Generator)나 Template Engine(Webpack)을 이용하여 Markup을 미리 생성

### Markup

1. HTML 직접 작성
2. 툴(Template Engine) 이용
3. **정적 사이트 생성기**(SSG) **→ Static HTML 생성**
`Hugo(go)`, `Nuxt(vue)`, `Next(react)`, `Gatsby`

미리 작성된 `Static HTML`은 웹서버의 리소스 쓸 필요 X → 사용자에게 HTML만을 전달

`Static HTML`을 `CDN(Content Deilvery Network)`을 통해 `Cache`하고 배포 ⇒ **빠른 속도**

따로 동적으로 HTML을 생성하지 않음 → 웹서버 필요 X ⇒ **서버 비용** 낮음

모든 HTML이 Static HTML만으로 이루어지지 않음

모든 Markup을 정적으로 유지 → 최신 데이터 유지하기 어려움

최대한 HTML Build를 빌드하여 Cache하고 First meaningful paint의 속도 높이기 ⇒ 중요!!

### 모든 상황에 적절하진 않다

1. 워드프레스와 같은 서버사이드 CMS와는 사용하기 어려움
2. Ruby on Rails, Express등과 같은 백엔드 언어로 작성되어 서버와 웹 애플리케이션이 분리되지 않고 하나로 운영되고 있는 상황에서는 사용하기 어려움
3. isomorphic rendering으로 운영되는 웹 애플리케이션에는 적절하지 않다.