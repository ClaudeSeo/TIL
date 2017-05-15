# Find wrong code


## Question
```html
<!DOCTYPE html>
<html lang="ko">
    <head>
        <meta charset="utf-8">
        <style>
            .notice {
                font-size: 1.2em;
            }
            #world {
                color: red;
            }
        </style>
    </head>
    <body>
        <script>
            document.getElementById("menu").style.marginBottom = "10px";
            document.getElementsByClassName("notice").style.color = "red";
        </script>

        <ul>
            <li id="menu" class="about">
                소개
            </li>
            <li id="menu" class="notice">
                공지사항
            </li>
            <li id="hello world" class="board">
                게시판
            </li>
        </ul>
    </body>
</html>
```

## Answer
- `getElementsByClassName` 는 `Array` 형태로 반환되기 때문에 바로 `style` 속성을 수정할 수 없다
- `id` 값은 중복, 중첩이 불가능하다
- `Script` 가 상단에 있어서 `DOM` 이 랜더링 되기 이전에 `script` 가 동작하므로 `TypeError` 가 발생한다
- 만약 `script` 가 하단에 있어 정상적으로 동작했을 때, `#menu marginBottom`은 첫번째 `DOM` 인 `소개`만 적용된다
- `Script` 를 상단에서 실행시키려면 `document ready` 이벤트를 `catch` 하도록 한다

## 참고
- [aeun](https://github.com/aeun)