# gh-pages 배포하기
vue-cli 로 개발된 프로젝트를 github pages 배포하는 방법 정리


- config/index.js
    + assetsPublicPath 수정
    + 소스맵을 끄려면 productionSourceMap 를 false 로 변경
```javascript
build: 
    assetsSubDirectory: 'static',
    assetsPublicPath: '/portfolio/',
    productionSourceMap: false,
  }
```

- src/router.index.js
    + 아래의 코드를 추가
```javascript
export default new Router({
    base: '/portfolio'
})
```

- package.json
    + 스크립트 추가
```json
"scripts": {
    "deploy": "gh-pages -d dist/"
}
```

- `yarn build` 후 `yarn deploy` 를 하면 배포가 된다.