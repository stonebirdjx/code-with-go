# 封面
# 项目名称
## 项目布局
```bash
# 大致项目大致
blue-bird
    cmd
        cmd.go
        server.go
        version.go
    internal # 程序单独包
        http
            http.go
        grpc
            grpc.go
    pkg  # 程序公共包
        consts
            consts.go
        config
            config.go
        cache
           cache.go
           user.go
        model
            model.go
        observable
            metrics
            logs
            traces
            observable.go
        utils
            funcs.go
            version.go
            utils.go
    configs # 配置文件
        server.yaml
    main.go # 程序入口
    go.mod
    go.sum
    build.sh # linux编译脚本
    README.md # README 文件
    CHANGELOG.md
    LICENSE
    .gitignore
```
> 非必要的文件，不要放在项目的根目录下
>
> 每个文件只做与文件名相关的事情
## 协议
## 文件头注释
## 包注释
## 代码安全规范

# 简单的main函数
# 编译脚本
# 配置文件
# 面向接口编程
# mock
# 代码测试
# 命令行参数
# 监听信号优雅停机
# common包

# 系统可观测
## 调用链Trace
## 指标metric
## 日志log

# 服务系统
# 存储系统
# 缓存系统
# RecordHistory
# 变更通知系统
# 安全系统
# 限速系统


# 引用
# 结语