# go-martini

## Getting Started
```bash
$ go get github.com/go-martini/martini
```

```go
package main

import (
    "fmt"
    "github.com/go-martini/martini"
)

func main() {
    m := martini.Classic()
    m.Get("/", func() string {
        return "Hello world!"
    })
    m.Group("/api", func(r martini.Router) {
        r.Get("/projects", GetProjects)
        r.Post("/projects", CreateProject)
        r.Get("/projects/(?P<id>[0-9]+)", GetProject)
        r.Delete("/projects/(?P<id>[0-9]+)", DeleteProject)
        r.Put("/projects/(?P<id>[0-9]+)/archive", ArchiveProject)
        r.Put("/projects/(?P<id>[0-9]+)/restore", RestoreProject)
    })
    addr := fmt.Sprintf("%s:%d", "127.0.0.1", 8080)
    m.RunOnAddr(addr)
}
```
