# 깃 fork 후 원본 코드와 동기화
```
$ git clone https://github.com/ClaudeSeo/dev-meetup.github.io.git

$ git remote add upstream https://github.com/dev-meetup/dev-meetup.github.io.git

$ git remote -v
origin  https://github.com/ClaudeSeo/dev-meetup.github.io.git (fetch)
origin  https://github.com/ClaudeSeo/dev-meetup.github.io.git (push) 
upstream    https://github.com/dev-meetup/dev-meetup.github.io.git (fetch)
upstream    https://github.com/dev-meetup/dev-meetup.github.io.git (push)

$ git fetch upstream

$ git checkout master

$ git merge upstream/master
```

## 참고
- https://help.github.com/articles/syncing-a-fork/
