# Apex 로그, 롤백

## 로그
```bash
# 전체 로그 조회
$ apex logs hello

# -s 옵션을 통해 시간을 지정해서 조회할 수 있다.
$ apex logs hello -s 1h

# -f 옵션을 사용하면 로그를 추적해서 볼 수 있다
$ apex logs hello -f

# 함수에 대한 메트릭 조회를 할 수 있다
$ apex metrics hello
```

## 롤백
```bash
# AWS Lambda function 에 버전 관리 기능이 없지만, apex이 제공하고 있으므로 잘못 배포했으면 되돌리면 된다
$ apex rollback hello

# 삭제
$ apex delete hello
```
