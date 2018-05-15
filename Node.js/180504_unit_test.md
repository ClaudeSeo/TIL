# 단위 테스트
회사에서 쓰는 테스트에 대해 공부해봅시다

## 사용하는 라이브러리
- mocha: 자바스크립트 테스트 프레임워크
- should: BDD 스타일의 비교 라이브러리
- sinon: Mock 라이브러리

## 용어 정리
- 테스트 더블 (Test Double): 테스트하기 어려운 경우 이를 대신해 테스트를 진행할 수 있도록 만들어주느 객체를 의미한다.
- 더비 객체 (Dummy Object): 단순히 인스턴스화 된 객체가 필요할 때 사용하며, 객체의 기능이 필요한 경우 다른 테스트 객체를 생성해야된다.
- 테스트 스텁 (Test Stub): 더비 객체보다 좀 더 구현화된 객체이며, 상태검증을 할 때 사용한다. 특정 
- 상태를 정의해놓고 사용하기 떄문에 값의 변경은 테스트 할 수 없다.
- 페이크 객체 (Fake Object): 여러개의 인스턴스를 대표하거나 좀 더 복잡한 구현이 들어가있는 경우 사용한다.
- 테스트 스파이 (Test Spy): 테스트에 필요한 객체에 대해서 특정 개체가 제대로 호출되었는지, 몇번 호출되었는지 등을 감시하고 있다가 특별한 호출이 들어올경우 정보를 전달해준다. 일반적으로 테스트 스파이를 잘 사용하는 경우는 없다. (Mock 객체가 더 편리하기 떄문이다)
- Mock 객체 (Mock Object): 행위 검증을 할 때 사용하는 객체이며, 테스트 더블의 하위 객체로의 좁은 의미와 테스트 더블을 포함한 넓은 의미 2가지로 사용된다. 행위 검증은 복잡도가 높거나 정확하게 작성하기 어렵기 때문에 상태검증으로 대체가 가능한 경우 행위 검증 테스트 코드는 작성하지 않는다.

## mocha
`Runner` 를 포함하고 있는 테스트 프레임워크로 사용자가 가장 많은 테스트 프레임워크이다.

`mocah` 자체는 `assertion` 을 지원하지 않기 때문에 별도의 라이브러리가 필요하다. Node.js 에서 기본적으로 지원하는 `assert` 라이브러리를 사용할 수 있으며 최근에는 `chai`, `should` 라이브러리들과 함께 사용한다고 한다.

- package.json 스크립트에 넣어두면 편리하다 (필수는 아님)
```bash
$ yarn add global mocha
$ vim package.json
"scripts": {
  "test": "mocha $(find ./ -name '*.spec.js') --recursive -w"
},
```

```javascript
describe('calc.js 테스트', () => {
    describe('sum 함수 테스트', () => {
        it('1과 2를 매개변수로 전달하면 3이 반환된다', () => {
            const result = sum(1, 2)
            assert.equal(result, 3);
        })
    })
})
```

## should
should.js 는 독창성있고 가독성이 좋으며 프레임워크에 의존적이지 않은 BDD 스타일의 Assertion 라이브러리 이다.
Node.js에서 제공하는 `assert` 라이브러리를 확장해 만든 라이브러리 이기 떄문에 기존 assert 모듈과 동일하게 사용할 수 있다.

```bash
$ yarn add should
```

```javascript
const should = require('should')
const a = 1

should.strictEqual(a, 1) // true
a.should.equal(1) // true
```

- assertion이 실패했을 경우 좀 더 정확하게 내용을 전달해주기 추가적인 설명을 적을 수 있다.
```bash
> const a = 1
> a.should.equal(2, '내가 왜 실패했는지 모르겠네요..')
AssertionError: 내가 왜 실패했는지 모르겠네요..
   ...
```

## 주의사항
- Mock 프레임워크가 실제로 필요한지 검토해보고, 필요하다면 의존성이 적은 구조로 프로그래밍 한다.
- Mock 객체는 실제 객체를 대신하여 흉내낸 객체일뿐 실제로 동작하지 않을 가능성이 있다.