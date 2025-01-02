# 命令行参数
命令行参数是一种从命令行获取输入的方法，可以用于运行程序时传递信息给程序，推荐使用命令行参数来启动程序。

在golang 程序中推荐使用 Cobra 包来控制程序, Cobra 已使用于多种大型项目的命令行参数 Kubernetes,Hugo, and GitHub 等. 

使用方式查看 https://github.com/spf13/cobra
```bash
bluebird version
bluebird --help
# server
bluebird server start -c configs/server.yaml
bluebird server stop

# other
bluebird other -arg1 value 1 -arg2 value2
```