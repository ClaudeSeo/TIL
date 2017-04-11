# 깃 repository 셋팅하기

## 새로 프로젝트를 시작하는 경우
```
$ git clone https://github.com/ClaudeSeo/TIL.git
```

## 기존 프로젝트가 있는 경우
```
$ git init

$ git add .

$ git ci -m "Initialize"

$ git remote add origin https://github.com/ClaudeSeo/TIL.git

$ git remote -v

$ git push -u origin master
origin	https://github.com/ClaudeSeo/TIL.git (fetch)
origin	https://github.com/ClaudeSeo/TIL.git (push)
```