[TOC]

# 安装&配置
#### Mac OS

在 https://golang.org/dl/ 下载安装程序。双击开始安装并且遵循安装提示，会将 Golang 安装到 /usr/local/go 目录下，同时 /usr/local/go/bin 文件夹也会被添加到 PATH 环境变量中。

#### Windows

在 https://golang.org/dl/ 下载 MSI 安装程序。双击开始安装并且遵循安装提示，会将 Golang 安装到 C:\Go 目录下，同时 c:\Go\bin 目录也会被添加到你的 PATH 环境变量中。

#### Linux
在 https://golang.org/dl/ 下载 tar 文件，并解压到 /usr/local。

请添加 /usr/local/go/bin 到 PATH 环境变量中。Go 就已经成功安装在 Linux 上了。


# GO的开发环境

### 1. 建立工作区
在go1.11版本之前，默认使用GOPATH的开发模式，在go1.11版本中Module是可选方式。

在 Mac 或 Linux 操作系统下，Go 工作区默认设置在 $HOME/go。所以我们要在 $HOME 目录下创建 go 目录。但是我们可以通过修改 GOPATH 环境变量修改工作区位置。

而在 Windows 下，工作区默认设置在 C:\Users\YourName\go。所以请将 go 目录放置在 C:\Users\YourName。同样也是可以通过修改GOPATH环境变量重置工作区位置。

工作区目录如下

```
GOPATH/
    src/
        golang.org/x/net/
            .git/
            html/
                parse.go
                node.go
                ...
    bin/
        helloworld
        dup
    pkg/
        darwin_amd64/
        ...
```

- src<br>
    其中src子目录用于存储源代码
    每个包被保存在与$GOPATH/src的相对路径为包导入路径的子目录中，例如 gopl.io/ch1/helloworld 相对应的路径目录。
- bin<br>
    保存编译安装的可执行文件
- pkg<br>
    其中pkg子目录用于保存编译后的包的目标文件
    

### 2. 几个重要的环境变量

```
$ go env
GOPATH="/home/gopher/gobook"
GOROOT="/usr/local/go"
GOARCH="amd64"
GOOS="darwin"
...
```

- GOROOT用来指定Go的安装目录，还有它自带的标准库包的位置
- GOPATH环境变量，用来指定当前工作目录

### 3. IDE
VSCODE

VIM


# 一个完整的GO程序

```
// 目录结构
// $GOPATH/src/
//      git.staff.sina.com.cn/
//          mars/
//              phoenix/
//                  demo/
//                      main.go

package main

import "fmt"

func main() {
    fmt.Println("hello world!")
}
```


```
go run .
go build git.staff.sina.com.cn/mars/phoenix/demo
go install git.staff.sina.com.cn/masrs/phoenix/demo
```

