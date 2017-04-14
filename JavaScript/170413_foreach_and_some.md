# forEach and some
JavaScript 에서도 컬렉션의 요소를 반복할 수 있는 forEach 문이 존재한다. 사용법은 간단하다

```javascript
[1,2,3,4,5].forEach(function (v) {
    console.log(v)
})

>> 1
>> 2
>> 3
>> 4
>> 5
```

forEach문에서는 중간에 반복을 중단할 수 있는 `break` 문이 없다.

Error Exception을 발생시켜 멈추는 변태적인 방법이 있지만, 아래의 예제에서 보다시피 굉장히 지저분하고 가독성이 안좋다.

```javascript
var StopException = new Error('StopException')
try {
    [1,2,3,4,5].forEach(function (v) {
        console.log(v)
        if (v == 2) {
            throw StopException
        }
    })
} catch (e) {
    if (e !== StopException) {
        throw e
    }
}

>> 1
>> 2
```

이를 대신해서 사용할 수 있는 함수가 바로 `some()` 이다.
`some()` 함수는 반복하는 도중 `true` 값이 반환되면 반복을 중단한다.

```javascript
[1,2,3,4,5].some(function (v) {
    console.log(v)
    return v == 2
})

>> 1
>> 2
>> true
```
