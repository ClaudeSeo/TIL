# 깃 repository 셋팅하기

## 새로 프로젝트를 시작하는 경우
```
$ git clone https://github.com/ClaudeSeo/TIL.git
```

## 기존 프로젝트가 있는 경우
```
$ git init

$ git add .

$ git commit -m "Initialize"

$ git remote add origin https://github.com/ClaudeSeo/TIL.git

$ git remote -v
origin	https://github.com/ClaudeSeo/TIL.git (fetch)
origin	https://github.com/ClaudeSeo/TIL.git (push)

$ git push -u origin master
```

## 참고
- https://help.github.com/articles/adding-an-existing-project-to-github-using-the-command-line/
