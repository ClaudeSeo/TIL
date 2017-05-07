## Vue EventBus

## EventBus
일반적으로 한 컴포넌트 내에서 변수, 메서드 등이 정의되기 때문에 이벤트를 사용할 필요 없이 바로 호출하여 사용할 수 있다

하지만, 서로 다른 컴포넌트에서 데이터를 전송하거나 함수를 호출하려면 어떻게 해야할까? 서로 데이터를 주고 받을 수 있는 공간을 만들고, 이를 통해 정해진 규격에 맞춰 데이터를 주고 받으면 된다

데이터를 받을 컴포넌트에서 이벤트를 청취(on) 하고 있으면, 다른 컴포넌트가 이벤트를 발생(emit) 시킬 때 전송하는 데이터를 받아서 로직을 수행한다

```vue
// 이벤트 버스 생성
let EventBus = new Vue()

// 이벤트 청취
EventBus.$on('my-event', (message) => {
    console.log(message)
})

// 이벤트 발생
EventBus.$emit('my-event', '뾰로롱뾰롱 뾰로로롱')
```
        
## 예제
```vue
<div id="sender-app">
  <input type="text" v-model="text">
  <button @click.prevent="sendMessage">전송</button>
</div>

<div id="receiver-app">
    <p v-if="text">
        receiver: {{ text }}
    </p>
</div>
```

```javascript
let EventBus = new Vue()

let SenderApp = new Vue({
    el: '#sender-app',
    data () {
        return {
            text: ''
        }
    },
    methods: {
        sendMessage () {
                EventBus.$emit('message', this.text)
      }
    }
})

let ReceiverApp = new Vue({
    el: '#receiver-app',
    data () {
        return {
            text: ''
        }
    },
    created () {
        EventBus.$on('message', (text) => {
            this.text = text
        })
    }
})
```

위의 예시에서 확인할 수 있드시 SenderApp, ReceiverApp이 다른 App 임에도 불구하고 정상적으로 데이터를 공유할 수 있다

## EventBus plugin
```javascript
let EventBusPlugin = {}

EventBusPlugin.install = (Vue, options) => {
    const eventBus = new Vue()

    Vue.eventBus = eventBus
    Vue.prototype.$eventBus = eventBus
}

export default EventBusPlugin
```

```javascript
import EvnetBusPlugin from './plugins/bus'

Vue.use(EvnetBusPlugin)
```

```vue
<template>
    <p v-if="text">Receiver: {{ text }}</p>
</template>
<script>
export default {
    name: 'my-component',
    data () {
        return {
            text: ''
        }
    },
    created () {
        this.$eventBus.$on('message', (text) => {
            this.text = text
        })
    }
}
</script>
<style scoped>
</style>
```

## 참고
- [Demo](https://jsfiddle.net/ClaudeSeo/9Lgys9sf/)
- https://github.com/ClaudeSeo/TIL/blob/master/JavaScript/170507_vue_plugin.md
- https://vuejs-kr.github.io/jekyll/update/2017/02/13/vuejs-eventbus/