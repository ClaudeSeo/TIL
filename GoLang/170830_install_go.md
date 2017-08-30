# Mac에 Go Lang 설치하기

## 설치방법
1. [http://golang.org/dl](http://golang.org/dl) 사이트에 젒속하여 Mac 용 패키지 (.pkg) 를 다운받는다
2. 다운로드 받은 패키지를 실행하고, 해키지 설치화면이 나오는 Wizard 를 따라 설치한다
3. 터미널을 실행시킨 후, `~/.zshrc` 하단에 `export PATH=$PATH:/usr/local/go/bin` 코드를 추가한 후 저장한다
4. 아래의 커맨드를 실행한다.
```bash
$ source ~/.zshrc
$ go version
go version go1.9 darwin/amd64
```

## Hello World
```bash
$ vim hello.go
```

```go
package main
import "fmt"

func main() {
    fmt.Printf("Hello World\n")
}
```

```bash
$ go run hello.go
Hello World
```
