# Sequelize.js
Sequelize.js 는 Node.js  기반의 ORM (Object-Relational-Mapping) 이다.

[Sequelize.js](http://docs.sequelizejs.com/) 는 Node.js v4 이상에서 사용이 가능하며, Promise 를 기본으로 동작한다.

## 공식 지원 DBMS
- MySQL / MariaDB
- PostgreSQL
- SQLite
- MS-SQL

## 설치
- Sequelize 는 DBMS 패키지를 포함하고 있지 않으므로 사용하려는 DBMS 패키지를 별도로 설치해야된다
```bash
$ yarn add sequelize
$ yarn add mysql
```


## 설정
```javascript
const Sequelize = require('sequelize');
const sequelize = new Sequelize(
    'til', // DB 이름
    'username', // 유저 명
    'password', // 비밀번호
    {
        host: 'localhost', // 데이터베이스 호스트 ( defualt localhost )
        dialect: 'mysql' // DBMS 종류
    }
);

```


## 모델 생성
```javascript
sequelize.define('TIL', {
    id: {
        type: Sequelize.INTEGER,
        primaryKey: true,
        autoIncrement: true
    },
    content: {
        type: Sequelize.STRING,
        allowNull: false 
    },
    create_ts: {
        type: Sequlieze.INTEGER,
        allowNull: false,
        default: 0
    }
})
```


## 데이터 추가
```javascript
TIL.create({
    content: 'Practive of Sequelize.js',
    create_ts: new Date().getTime()
})
```


## 데이터 조회
- `findOne()`, `findAll()` 메소드로 조회할 수 있다 
```javascript
TIL.findAll({
    where: {
        id: 1
    }
})
```


## 데이터 업데이트
```javascript
TIL.update({
    content: 'WOW'
}, {
    where: {
        id: 1
    }
})
```


## 데이터 삭제
```javascript
TIL.destory({
    where: {
        id: 1
    }
})
```


## 참고
- http://docs.sequelizejs.com/manual/installation/getting-started.html
    + 공식 Document 를 보는게 가장 좋다
- http://webframeworks.kr/tutorials/expressjs/expressjs_orm_one/
