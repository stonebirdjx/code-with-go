# 配置文件

go程序推荐使用yaml格式的配置文件，因为yaml比较简单，类型丰富，层次清晰，易读性强。


```yaml
bootstrap:
  port: 6789
  pprof: true
  log:
    dir: logs
    level: debug
    size: 100M

cache:
  - name: client
    size: 100
    ttl: 10
  - name: config
    size: 100
    ttl: 10

```

> 推荐 以 相关功能 为一块 配置。
