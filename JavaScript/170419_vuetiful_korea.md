# Vuetiful Korea (Vue.js 한국어 사용자 모임) 1회 모임
이 문서는 재 가공을 하지 않고 그냥 올릴테다!

## 목차
- 우당탕탕 회사에 Vue.js를 도입한 삽질기 - 박새미님
- 백엔드 개발자, 입문자로서 Vue 이해하고 사용하다 - 차경묵님
- 웹 디자이너의 도전 Vue.js 따라하기 - 이승민님
- Vue.js와 Firebase 활용기 - 김인숙님
- Nuxt로 사내 서비스 구현하면서 얻은 경험 공유 - 조민환님

## 우당탕탕 회사에 Vue.js를 도입한 삽질기
- 국내 최고 광고 차단 어플 유니콘 개발자
- 관리자 페이지를 Vue.js로 개발하고 실제 서비스 중
- 주제: Vue.js를 사용해서 프로젝트를 진행한 경험 공유
- Vue.js를 도입한 이유
	+ 주먹구구식 코드 작업으로 인해 관리가 안되는 코드
	+ React.js 도입 실패로 인한 시간 손실
		* 컴포넌트 구조에 대한 이해 부족
		* 한번에 모든걸 적용하려고 이것저것 도입
	+ 가장 적은 비용으로 도입이 가능할 것 같아서
		* 가장 큰 장점: 공식 홈페이지가 한글이고, 바로 검색해서 자료를 찾을 수 있다.
		* 단일 파일내에 모든 작업을 할 수 있다. ( 단일 파일 컴포넌트 )
	+ 심플하면서 모든 기능을 가지고 있어서
	+ 회사에서 우려한 사항
		* 대중적이지 못하고, 인수인계에 대한 어려움이 생길 가능성이 높다
		* Vue의 메이저 후원사 여부
	+ 도입 과정
		* 구매한 Bootstrap 테마가 적용 가능한 테마 예제 확보 ( Vue Admin LTE Theme )
		* Bootstrap 테마 적용 및 프로젝트 구조 잡기
			- 사용된 jQuery 라이브러리로 인한 지저분한 코드
			- Router 페이지 이동 처리
			- Rest Paameter 데이터가 없을 때 404 처리
		* 단일 컴포넌트로 구성된것들을 재사용 되는 컴포넌트를 기준으로 분리
		* 레거시 코드들을 순수 vue 코드로 변환할 예정
- 도입 후 느낀점
	+ 문서만 보고 사용할 수 있을 정도의 프레임워크
	+ 한글 문서가 굉장히 매력적이다
	+ jQuery의 늪
	+ JavaScript의 this가 항상 어렵게 느껴진다
	+ 컴포넌트 기반의 작업에 대한 두려움이 사라졌다
	+ 삽질이 답이다

## 백엔드 개발자, 입문자로서 Vue 이해하고 사용하다
- Python back-end 개발자 ( Prototype.js, jQuery 세대 )
- Vue.js를 도입한 이유
	+ React, Angular.js에 비해 덜 유명한거 같아서
		* 생태계에 들어와보니 사용자가 생각보다 많아서 실망(?)
	+ 공식 문서의 글투가 다정해서
	+ 전환 비용이 낮아서
		* EJS + jQuery ==> Vue.js
- 주제: back-end 개발자가 front-end 개발 사고를 익혀가는 명랑 성장기
- 개념 비유
	+ 프리젠테이션
	+ 스프레드시트
- 반응형 동작과 동기식 동작
	+ 특정 데이터의 상태에 의존하는 동작(behavior)은 예상과 의도대로 동작하지 않기도 한다
	+ 데이터의 의존 관계와 계층 구조 설계가 필요하다
		* UI가 반응할 데이터의 의존과 계층 구조를 고민
	+ 데이터를 제어하여 UI 요소를 제어한다는 관점 전환 
- 반복되는 코드
	+ UI 요소를 단위 요소로 보지 않고, 데이터 제어 수단으로 접근한 기존 관점
		* 템플릿 코드가 길어져 *.vue 편집이 불편하다
	+ 동일 목적당 한 단위 컴포넌트로 작성
- 컴포넌트
	+ 재사용 가능한 UI 요소 단위 
	+ UI 요소를 개체화하여 재사용성과 의존성 관리 
		* Python의 웹 프레임워크인 Django 의 App과 유사 
	+ 재 사용의 JavaScript 코드 단 의미
		* 컴포넌트의 `data`가 함수인 이유는?
			- 컴포넌트의 기준은 *재사용성* 인데, Object로 사용하게 될 경우 데이터가 참조되어 컴포넌트간의 영향을 줄 수 있기 때문이다
	+ store 패턴, slot
- REST API 관점 변화
	+ SSR
		* 표현단에 데이터를 전달하는 방법은 다소 느슨하고 게으르게 접근
	+ RESTfulAPI 구현
		* UI 표현에 필요한 데이터를 전달
	+ 변화하는 관점
		* UI가 반응할 데이터에 필요한 데이터를 고민
- Vue.js는 React에 비해 상대적으로 변화가 적은편이다

## 웹 디자이너의 도전 Vue.js 따라하기
- 알고랩 디자이너
- 단일 페이지인데 jQuery로 모든 상태 변화 처리 ( 코드는 약 4,000라인 )
- jQuery 보다 좋아보이고, React 보다 쉽고 좋아보여서 사용하기 시작
- 02:05:29 + a 정도 시간을 투자하여 공부
- 디자이너도 조금만 노력하면 쉽게 접근할 수 있다

## Vue.js와 Firebase 활용기
- 가비아 프론트엔드 개발팀
- Vue.js를 도입한 이유
    - 다른 프레임워크에 비해 러닝코스트가 적게 든다
    - 단일 파일 컴포넌트 (*.vue)
    - 유연함
    - 가벼움
    - 한국어 가이드 문서가 잘되어 있음
- Firebase를 선택한 이유
    + 웹, iOS, Android 개발에 필요한 서비스를 제공하는 BaaS (Back-end As A Service)
    + 직접 back-end를 구성할 필요가 없어 시간 단축에 도움
- 개발 프로세스
    + FireBase 셋팅
    + Vue.js 셋팅
    + 프로젝트에 필요한 라이브러리 추가
        * VueFire
        * firebase
        * firebase-tools
        * vue-blu
    + FireBase 연결
    + 빌드 
    + 배포 

## Nuxt로 사내 서비스 구현하면서 얻은 경험 공유
- 데브시스터즈 웹셀 프론트엔드 개발자
- React 의 Next.js : Vue 의 Nuxt.js
- Web Development Nowaday
    + Component, Container, Store
    + SSR
    + Router W/History API
    + ECMAScript
    + Hot Module Reloading
    + SASS
- Full Packages === Nuxt.js
- Isomorphic JavaScript
    + 주의할점
    + Diffrent Context
    + Tree Shaking
- REST API Mocking Tool: json-server
- JavaScript를 차단하더라도 일정 부분 컨텐츠를 제공할 수 있음
- 생산성이 정말 좋아짐