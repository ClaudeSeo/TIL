# async-await
Node.js는 JavaScript를 사용하며 Non-block I/O, 단일 스레드 이벤트 루프를 사용하여 높은 퍼포먼스를 자랑하는 언어이다.

Node.js로 비동기식 코드를 작성하면 아래와 같은 코드가 나온다
```javascript
request('http://naver.com', (error, response, body) => {
    success(body)
})
```

callback이 위와 같이 단순하다면 크게 문제가 없으며, 점점 요구사항이 복잡해지면서 **Callback Hell** 이 시작된다

```javascript
request('http://naver.com', (error1, resp1, body1) => {
    request('http://google.com', (error2, resp2, body2) => {
        request('http://daum.net', (error3, resp3, body3) => {
            success(body1, body2, body3)
        })
    })
})
```

당장 위의 코드만 봐도 굉장히 답답함을 느낄 수 있다. 이러한 문제들을 해결하기 위해 많은 움직임들이 있었고, 2014년 차기 ES6 자바스크립트 규격에 `Promises/A+`` 스펙이 확정되면서 어느정도 해결되었다

```javascript
Promise.all([
    request('http://naver.com'),
    request('http://google.com'),
    request('http://daum.net')
]).then(success, error)
```

하지만, 더 복잡한 로직의 어플리케이션을 개발하다보면 Promise 도 복잡해져서 코드 읽기가 굉장히 힘들어지는 상황이 왔다.

이러한 상황을 해결하기 위해 C# 에서 비동기 통신을 구현할 때 사용하는 `Async/Await` 문법을 JavaScript에 도입하기로 했고, Node.js 7.6+ 부터 정식으로 지원하고 있다.

```javascript
async function doComplicateJob() {
    const naver = await request('http://naver.com')
    const google = await request('http://google.com')
    const daum = await request('http://daum.net')
    console.log(daum)
    return {naver, google, daum}
}

doComplicateJob().then(success, error)
```

`async-await`의 본질은 `Promise` 이다. async 지시자가 붙은 함수는 반드시 Promise를 반환한다.

또한 await 지시자가 붙은 Promise는 `<Pending>` 상태에서 `<Resolved>` 혹은 `<Rejected>` 로 상태가 변화할 때 까지 기다려준다.

`async-await`를 사용한다고 Synchronize 동작하는것은 아니지만, 마치 동기식 코드인것처럼 읽을 수 있게 된다.

이전에 10중 **Callback Hell**을 맛보고 나서, 어떻게 해야 깔끔하게 작성할 수 있을까 고민하고 있었는데 `Promise` 와 `async/await`를 사용해보니 이전에 비해 훨씬 깔끔하게 작성할 수 있게 되었다.

## 참고
- http://tc39.github.io/ecmascript-asyncawait/
- http://blog.naver.com/PostView.nhn?blogId=bitofsky&logNo=220850909832&categoryNo=0&parentCategoryNo=53&viewDate=&currentPage=1&postListTopCurrentPage=1&from=postView
