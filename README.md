# go-learn

v1

## 入口文件

新建main.go

```go
package main

import "fmt"

func main() {
	fmt.Println("Hello World")
}
```
**注意**：go中不能使用单引号

## 模块依赖

新建app文件下，新建utils文件夹，新建sum文件

app/utils/sum.go

```go
package utils

func Sum(a, b int) int {
	return a + b
}
```

想在main.go中引用这个sum方法

需要初始化整个项目

```shell
go mod init
```

init 后面可以加上项目名称，没写默认就是项目名

在main.go中引用sum

main.go

```go
package main

import (
	"fmt"
	"goLearn/app/utils"
)

func main() {
	var num = utils.Sum(1, 1)
	fmt.Println("sum result: ", num)
}
```

## 执行

终端中执行 `go run main.go`