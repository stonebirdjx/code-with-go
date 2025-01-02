# 退出状态码
退出状态码都有特殊的意义，用来显示命令退出时的状态，更多地给外部使用．shell退出状态码是一个0~255之间的整数值．通常成功返回0，失败返回非0(错误码)．

linux 退出状态码 

- 0：成功（Success），程序成功完成，无错误。
- 1：通用错误（General error），一般性错误，通常表示命令执行失败。
- 2：误用命令（Misuse of shell builtins），命令的用法错误，例如，缺少必要的参数。
- 126：命令不可执行（Command invoked cannot execute）， 尝试运行一个不可执行的命令，例如权限不足。
- 127：命令未找到（Command not found），尝试运行一个不存在的命令或脚本。
- 128：无效的退出参数（Invalid exit argument），使用了无效的退出状态码。
- 130：进程被 Ctrl+C 终止（Script terminated by Control-C），进程接收到 SIGINT 信号（中断信号）。
- 137：进程被 kill 命令终止（Script terminated by SIGKILL），进程接收到 SIGKILL 信号，通常是使用 kill -9 终止的。
- 139：段错误（Segmentation fault），进程因段错误（非法内存访问）而终止。
- 143：进程被 SIGTERM 终止（Script terminated by SIGTERM），进程接收到 SIGTERM 信号，通常是使用 kill 终止的。
- 255：退出状态码超出范围（Exit status out of range），一般表示程序返回了超出范围的退出状态码。

使用方式
```go
// main.go
func main() {
    cmd.Execute()
}

// cmd/version.go
var versionCmd = &cobra.Command{
	Use:     "version",
	Short:   "Print the client and server version information for the current context.",
	Example: `  bluebird version`, // 保留两个空格
	Run:     versionRun,
}

func versionRun(cmd *cobra.Command, args []string) {
	fmt.Println(consts.Version)
	os.Exit(consts.ExitCodeSuccess)
}
```