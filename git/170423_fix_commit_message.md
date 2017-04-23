# Fix Commit Message
깃 커밋메시지를 작성하다보면 오타가 나거나 메시지를 잘못 적는 경우가 생긴다.

```bash
$ git add --all
$ git commit -m "update commetn"
```

이런 경우, `--amend` 옵션을 사용하여 커밋 메시지를 수정할 수 있다.

```bash
$ git commit --amend
  1 update commetn
  2
  3 # Please enter the commit message for your changes. Lines starting
  4 # with '#' will be ignored, and an empty message aborts the commit.
```

수정이 끝났으면 저장하고 종료하고 `git log -n 1` 명령어를 통해 확인해보면 된다.

```bash
$ git log -n 1
    update comment
```
