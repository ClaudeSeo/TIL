# Vue.js
흔히 알려진 MVC 패턴에서 View만 담당하는 프레임워크이다

## 설치
- 설치 방법은 CDN, NPM, Bower, AMD 모듈 로더 등이 있지만, 나는 NPM만 사용할것이다
- vue만 별도로 설치하여 프로젝트를 셋팅하는 방법이 있지만 `vue-cli` 라는 아주 훌륭한 툴을 제공하고 있으니 이를 통해 프로젝트를 셋팅한다
```
$ npm install vue-cli -g
$ vue init webpack <proejct-name>
$ cd <project-name>
$ npm install
$ npm run dev
```


## 파일 구조
프로젝트 생성할 때 지정하는 옵션에 따라 파일 구조가 달라질 수 있다
- /build : webpack build 설정 파일들 (vue-loader, babel-loader, webpack ...)
- /config : 환경 설정 파일들 (development, test, production)
- /src/assets : static 파일들 (이미지, 아이콘, 폰트 등)
- /src/components : 컴포넌트 파일들
- /src/router/index.js : vue-router 설정 파일
- /src/App.vue : Application 메인 컴포넌트
- /test : e2e, unit 테스트

## 컨셉
- 컴포넌트 내부에 HTML, CSS, JavaScript, Method, Data 를 묶어서 하나의 `*.vue` 파일로  구성
- 컴포넌트는 총 3가지의 영역 (Language Block)로 구성
    + `<template>`
        - HTML
        - Jade
        - Pug
    + `<script>`
        * JavaScript
        * TypeScript
        * CoffeeScript
    + `<style>`
        * sass
        * less
        * css
    + 각 블럭은 `script` 블럭에 정의된 `data`와 `method`를 공유함
    + `template` 블럭과 `script` 블럭은 양방향 데이터 공유가 가능
- vue는 컴포넌트의 조합으로 이루어지며 트리구조를 가지고 있음
    + 데이터는 부모 컴포넌트에서 자식 컴포넌트로 데이터를 `단방향`으로 전달함


## 맛보기
```vue
<template>
    <div class="container">
        <p>Hello {{ name }}</p>
    </div>
</template>
<script>
export default {
    name: 'main',
    data () {
        return {
            name: 'ClaudeSeo'
        }
    }
}
</script>
<style scoped>
.container {
    width: 100%;
    text-align: center;
}
</style>
```


## 참고
- https://kr.vuejs.org/v2/guide/installation.html#Bower
- https://www.slideshare.net/sunhyouplee/tour-of-vuejs-70654520


