# Vue Plugin
플러그인은 일반적으로 전역 수준 기능을 vue에 추가한다

## 플러그인 유형
1. 전역에서 사용하는 메서드 혹은 속성
2. 디렉티브, 필터, 전환 효과 등
3. 어디서든 접근 가능한 mixin
4. 인스턴스 메서드 추가
5. 원래 가지고 있는 api를 제공하면서 위의 기능들을 조합하여 제공하는 라이브러리

## 플러그인 추가
```javascript
let MyPlugin = {}

MyPlugin.install = (Vue, options) => {
    // 1. 전역에서 사용하는 메서드 혹은 속성
    Vue.globalMethod = () => {
        ...
    }

    // 2. 디렉티브, 필터, 전환 효과 등
    Vue.directive('my-directive', {
        bind (el, biding, vnode, oldVnode) {
            ...
        } 
    })

    // 3. 어디서든 접근 가능한 mixin
    Vue.mixin({
        created () {
            ...
        }
    })

    4. 인스턴스 메서드 추가
    Vue.prototype.$myMethod = () => {
        ...
    }
}

export default MyPlugin
```

## 플러그인 적용
```javascript
import myPlugin from './plugins/myPlugin'

Vue.use(myPlugin)
```

## 참고
- https://kr.vuejs.org/v2/guide/plugins.html