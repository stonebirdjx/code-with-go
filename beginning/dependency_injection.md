# 依赖注入

依赖注入 (Dependency Injection，缩写为 DI)，可以理解为一种代码的构造模式（就是写法）

如果自己构造依赖关系， 则创建 与 行为 两个目的的代码容易耦合在一起， 代码较长，给理解造成困难。

**没有依赖注入的样子**
```go
type Interface interface {
    Get(id string) string
}

type App struct {
    Methods Interface
}

type Mongo struct {
    //...
}

func (m *Mongo) Get(id string) string {
    return "mongo"
}

type Mysql struct {
    //...
}

func (m *Mysql) Get(id string) string {
    return "mysql"
}

func NewApp() *App {
    var m Interface
    if somthing {
        m = NewMongo()
    }else{
        m = NewMysql()
    }

    return &App{
        Methods: m,
    }
}
```

**有依赖注入的样子**
```go  
func NewApp(m Interface) *App {
    // 把声明放在外面去
    return &App{
        Methods: m,
    }
}
```

> 喜欢代码生成的可以使用 wire， wire是由 google 开源的一个供 Go 语言使用的依赖注入代码生成工具。它能够根据你的代码，生成相应的依赖注入 go 代码。