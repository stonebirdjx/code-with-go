# 包注释
包注释紧贴package语句之上，且只在一个文件中加入，以Package name 开头，以. 结尾，包注释内容可在godoc上显示。

内容较少的可以放在与包名同名的文件中，内容较多的放在doc.go文件中。

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

// Package cmd provides a way to start a program with command line parameters
package cmd
```