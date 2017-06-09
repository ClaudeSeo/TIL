# Prompt Context
Custom prompt_context

## 커스터마이징
- 폴더 복사
    + oh-my-zsh 폴더는 git으로 관리되기 때문에 업데이트 시 충돌이 없으려면 custom 폴더에 복사해서 수정해야된다
```bash
$ cp ~/.oh-my-zsh/themes/agnoster.zsh-theme ~/.oh-my-zsh/custom/
$ vim ~/.oh-my-zsh/custom/agnoster.zsh-theme
```

- prompt_context 를 찾아서 아래의 코드로 변경한다
```
prompt_context() {
  if [[ "$USER" != "$DEFAULT_USER" || -n "$SSH_CLIENT" ]]; then
    prompt_segment black default "%(!.%{%F{yellow}%}.)$USER"
  fi
}
```

## 결과
- 변경 전
```bash
$ seodongmyeong@seodongmyeong-ui-MacBook-Pro ~
```

- 변경 후
```bash
$ seodongmyeong ~
```
