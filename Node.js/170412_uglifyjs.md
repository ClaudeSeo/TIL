# UglifyJS
uglifyjs는 주요 자바스크립트 라이브러리들에서 가장 많이 쓰이는 압축 라이브러리다

## 설치
```
$ npm install uglify-js -g
```


## 사용법
- output 파일은 기존의 파일명에서 .min 을 붙여주는것이 암묵적인 규칙이다
- 다양한 옵션들이 존재하므로 github 를 참고하여 필요한 옵션을 넣으면 된다
```
$ uglifyjs test.js -o test.min.js [options]
```

## 참고
- https://github.com/mishoo/UglifyJS2