# v-model IME 버그
`v-model` 디렉티브를 사용하면 `input`과 `textarea` 에 양방향 데이터 바인딩을 사용할 수 있다

```vue
<template>
    <div class="container">
        <input v-model="message">
        <p> {{ message }}</p>
    </div>
</template>

<script>
new Vue({
    el: '#app',
    data: {
        message: '안녕하세요'
    }
})
</script>
```

IME (Chinese, Japanese, Korea etc) 가 필요한 언어를 사용할 경우 `v-model` 이 제대로 업데이트 되지 않는 버그가 있다. [참고 링크](https://jsfiddle.net/kciter/b5qhxbfh/)

```
- Vue.js 공식 홈페이지
IME (중국어, 일본어, 한국어 등)가 필요한 언어의 경우 IME 중 v-model이 업데이트 되지 않습니다. 이러한 업데이트를 처리하려면 input 이벤트를 대신 사용하십시오.

- Vue.js github issue
v-model does not working properly with Korean chars (only with IE 11)
```

이 문제를 해결하기 위해서는 `input` 이벤트 혹은 `@blur` 를 사용해서 해결해야한다.

모든 `input` 태그에 이벤트를 바인딩 해주는건 굉장히 귀찮고 코드도 더러워지기 때문에 `custom directive` 를 만들어서 사용했다.

```vue
<template>
    <div id="app">
        <input v-typing="message">
        <p>{{message}}</p>
    </div>
</template>

<script>
Vue.directive('typing', {
    bind: function (el, binding, vnode) {
        var expression = binding.expression
        el.value = vnode.context[expression]
        el.addEventListener('input', function (e) {
            vnode.context[expression] = e.target.value
        })
    }
})

new Vue({
    el: '#app',
    data: {
        message: '안녕하세요'
    }
})
</script>
```

## 라이브러리
이선협님이 만드신 [`vue-ime-model`](https://github.com/kciter/vue-ime-model) 라이브러리를 사용하면 된다.

~~직접 플러그인으로 만들어서 배포를 하기 직전에 발견했다고 한다~~

## 참고
- [Vuejs 폼 입력 바인딩 기본 사용법](https://kr.vuejs.org/v2/guide/forms.html#기본-사용법)
- [@input 을 사용한 해결 방법](https://jsfiddle.net/kciter/tLz9gt4o/)
- [@blur 을 사용한 해결 방법](https://jsfiddle.net/posva/g94vLx3o/)
- [custom directive 를 사용한 해결 방법](https://jsfiddle.net/ClaudeSeo/79nkvvn9/10/)
