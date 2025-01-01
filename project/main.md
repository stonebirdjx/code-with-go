# 简单的main函数
main函数作为程序入口，通常在main.go中

> 一个go项目建议只有一个main包
```go
// Copyright 2024 The stonebirdjx. All rights reserved.
//
// Licensed under the Apache License, Version 2.0 (the "License");
// you may not use this file except in compliance with the License.
// You may obtain a copy of the License at
//
//      http://www.apache.org/licenses/LICENSE-2.0
//
// Unless required by applicable law or agreed to in writing, software
// distributed under the License is distributed on an "AS IS" BASIS,
// WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
// See the License for the specific language governing permissions and
// limitations under the License.

package main

import (
	_ "go.uber.org/automaxprocs"
	"github.com/stonebirdjx/bluebird/cmd"
)

func main() {
	cmd.Execute()
}

```

- 在容器环境中 存在 GOMAXPROCS 会错误识别容器 cpu 核心数的问题。必须引用
`_ "go.uber.org/automaxprocs"`

- 通常以命令参数作为启动逻辑，所有的逻辑写在cmd包中

