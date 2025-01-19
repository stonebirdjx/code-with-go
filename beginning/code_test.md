# 代码测试

代码测试 可以有效的发现并解决 代码问题，写代码测试的过程，不仅要注重功能的正确性，还要注重代码覆盖率和代码性能

测试时一般会自定义一些测试数据，为了不影响原包，建议将测试包的包名加上 _test 或者专门创建一个测试包 ,与原包区分

要注重接口编程 https://github.com/uber-go/mock 

```go
type Foo interface {
  Bar(x int) int
}

func SUT(f Foo) {
 // ...
}

func TestFoo(t *testing.T) {
  ctrl := gomock.NewController(t)

  m := NewMockFoo(ctrl)

  // Asserts that the first and only call to Bar() is passed 99.
  // Anything else will fail.
  m.
    EXPECT().
    Bar(gomock.Eq(99)).
    Return(101)

  SUT(m)
}
```

> 注重代码覆盖率 go test -cover ./stb_test

> 注册性能 go test -bench=IsPalindrome 