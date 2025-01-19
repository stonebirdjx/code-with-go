# 优雅停机
优雅停机是指接收到退出信号时，关闭应用程序，在规定的超时时间范围内，允许进行中的请求完成，拒绝新的请求进入。

```go
func gracefulShutdown(srv *http.Server, exitCh chan int) {
	signalChan := make(chan os.Signal, 1)
	signal.Notify(signalChan, syscall.SIGINT, syscall.SIGTERM, os.Kill)

	sig := <-signalChan
	log.Printf("catch signal, %+v", sig)

	ctx, cancel := context.WithTimeout(context.Background(), 4*time.Second) // 4秒后退出
	defer cancel()
	if err := srv.Shutdown(ctx); err != nil {
		log.Fatal("Server Shutdown:", err)
	}
	log.Printf("server exiting")
	close(exitCh)
}
```