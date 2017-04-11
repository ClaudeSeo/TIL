# 더 좋은 RESTful API를 위한 10가지 사례

## 1. 동사 대신 명사를 사용해라
| Resource.  | GET (read) | POST (create) | PUT (update) | DELETE 
| ---------- | ---------- | ------------- | ------------ | ------------
| /reviews   | 리뷰 목록들을 반환 | 리뷰 생성 | 모든 리뷰를 동시에 수정 | 모든 리뷰를 삭제
| /reviews/1 | 1번 리뷰 정보 반환 | Method not allowd (405) | 1번 리뷰 정보 수정 | 1번 리뷰 삭제

- 아래처럼 사용하지마라
```
/getAllReview
/getReview?id=1
/createReview
/deleteReview?id=1
```


## 2. GET 메소드와 쿼리 파라미터로 상태를 변경하지마라
```
GET /users/activate (x)
GET /users?activate (x)

PUT /users (o)
```


## 3. 복수형만 사용해라
단수, 복수형을 혼합하여 사용하지말고, 모든 리소드들은 복수형 명사만 사용해라
```
GET /user (x)
GET /users (o)

GET /review (x)
GET /reviews (o)
```


## 4. 리소스가 다른 리소스에 관계가 있을경우 하위 리소스를 사용해라
```
GET /users/1/reviews ( 1번 사용자의 리뷰를 전부 반환 )
GET /users/1/reviews/1 ( 1번 사용자의 1번 리뷰를 반환 )
```


## 5. HTTP Header를 사용해라
서버와 클라이언트는 통신을 하기 위해 필요한 정의된 포맷이 필요하며, HTTP Header에 정의되어야 한다.

```
- Content-Type : 전송 포맷 ( text/html, text/javascript, */* ... )
- Accept : 응답 가능한 포맷 ( text/html, text/javascript ... )
```


## 6. HATEOAS
- HATEOAS : Hypermedia as the Engine of Application State)
- API 응답값에 link를 제공하여 탐색을 쉽게할 수 있도록 한다
```
{
    "name": "ClaudeSeo"
    "links": [
        {
            "rel": "self",
            "href": "/api/v1/users/1"
        }
    ]
}
```


## 7. 정렬, 필터링, 필드 선택, 페이지네이션을 제공해라
- Filter : 고유 쿼리 파라메터를 통하여 필터링한다
```
GET /users?isActive=1
```

- Sort : desc(-), asc(+)로 표현하고 컬럼단위로 표현한다
```
GET /users?sort=+id
```

- Field : 필요한 필드들만 조회할 수 있는 기능을 제공한다
```
GET /users?fields=id,username
```

- Pagiantion : offset, limit 를 사용하여 페이지네이션 기능을 제공한다
    + limit : 반환할 데이터 갯수
    + offset : 몇번재부터 데이터를 조회할건지
```
GET /users?offset=10&limit=10
```


## 8. API에 버전을 사용해라
`v`를 prefix 로 가지며, 그 뒤는 정수만 사용한다
```
GET /api/v1
```


## 9. HTTP Staus code를 사용하여 에러를 반환해라
```
- 200 : 서버가 정상적으로 요청을 처리함
- 201 : 리소스가 성공적으로 생성됨
- 204 : 성공했지만, 응답값 없음. ( 주로 delete 에서 사용됨 )

- 400 : 잘못된 request가 들어옴 
- 401 : 권한 없음 ( authentication )
- 403 : 접근이 허용되지 않음 ( Authorization )
- 404 : 리소스를 찾을 수 없음
- 405 : 허용되지 않은 Method로 요청 ( Method not allow )

- 500 : 서버 내부 오류  ( Internal Server Error )
```


## 10. HTTP Method를 오버라이딩하여 사용해라
- X-HTTP-Method-Override 를 사용하여 RESTful API가 지원하지 않는 메소드를 구현할 때 사용한


## 참고 
- https://blog.mwaysolutions.com/2014/06/05/10-best-practices-for-better-restful-api/