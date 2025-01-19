# 面向接口编程

接口表示调用者和设计者的一种约定，只要你实现了这个方法，你就符合这个 接口。

在编程过程中，代码只需要关注接口返回的数据，而不需要关心接口的实现。逻辑上会更清晰，同时也方便代码测试

```go
type Reader interface {
    Read() ([]byte, error)
}

func ReadAll(r Reader) ([]byte, error) {
    return r.Read()
}

type OTTCache sturct {
    ID string
}

func (o *OTTCache) Read() ([]byte, error) {
    return []byte("ottcache"), nil
}

func main() {
    reader := &OTTCache{}
    if bytes ,err := ReadAll(&OTTCache{});err == nil {
        fmt.Println(string(bytes))
    }
}

```