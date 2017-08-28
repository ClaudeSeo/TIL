# Github flow
배포가 빈번하게 발생하는 프로젝트에 어울리는 브랜치 기반의 워크 플로우다.

![Github Flow](https://raw.githubusercontent.com/ClaudeSeo/TIL/master/git/github_flow.png)

## 작업 흐름
1. `master` 브랜치는 항상 즉시 배포가 가능한 상태를 유지한다
2. 새로운 작업을 시작할 때는 master 브랜치로부터 새로운 브랜치를 생성한다. 
3. 원격 브랜치에 코드를 수시로 푸시한다
4. 피드백이나 도움이 필요할 경우, 혹은 작업이 완료된 경우 `Pull Request` 를 생성한다
5. 작업한 내용에 대한 리뷰가 완료되면 `master` 브랜치에 `merge` 한다
6. `master` 에 `merge` 가 되면 즉시 배포를 진행한다


## 규칙
1. `master` 브랜치는 항상 배포가 가능한 상태를 유지해야한다
    - `master` 브랜치에 버그가 있을 경우 `HEAD` 를 이전으로 되돌린다
    - 테스트 코드가 없거나 실패한 코드는 `master` 브랜치에 `merge` 하지 않는것을 원칙으로 한다
2. 새로운 작업을 할 때는 `master` 브랜치에서 새로운 브랜치를 생성한다
3. 브랜치명은 다른 개발자가 봤을 떄 어떤 일을 하는지 알 수 있도록 명확히 작성한다
    - refactor-authentication
    - user-content-cache-key
    - make-retina-avatars
4. 생성한 브랜치는 명시된 기능 이외의 것을 수정하지 않는다
5. `master` 에 `merge` 가 된 후 배포를 진행한 후 정상 동작하는지 확인한다 


## 선행 조건
- 테스트 자동화
    + eg) Travis CI, Jenkins CI
- 배포 자동화
    + eg) fabric, Ansible, Capistrano

## 기타
- `git flow` 에 비해 굉장히 단순하고 간단하기 때문에 쉽게 도입할 수 있다
- `Pull Request` 는 최소 단위로 생성하는게 좋다
    + 너무 방대한할 경우 리뷰어가 굉장히 고통받고 힘들어한다
- 팀 내에서 개발 규칙을 정하여 `Wiki` 로 공유하는것도 좋은 방법이다


## 참고
-  https://guides.github.com/introduction/flow/
