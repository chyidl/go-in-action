Go Command Tutorial
===================
```
~ at ☸️  yogo-dev (spf)
➜ cd $GOROOT/pkg/tool/darwin_amd64/

<GOOS>_<GOARCH>

pkg/tool/darwin_amd64 at ☸️  yogo-dev (spf)
➜ ls
addr2line* asm*       cgo*       cover*     doc*       link*      objdump*   pack*      test2json* vet*
api*       buildid*   compile*   dist*      fix*       nm*        oldlink*   pprof*     trace*
```

* go build
> 编译源码文件或代码包以及依赖包
```
Go语言源码文件三类:
    1. 命令源码文件     [可执行程序的入口]
    2. 库源码文件       [集中放置各种被使用的程序实体]
        > go build 命令在编译只包含源码文件的代码包时只会做检查性的编译，而不会输出任何结果文件
    3. 测试源码文件     [程序实体的功能和性能进行测试]

# 执行构建的包名打印
➜ go build -v hello.go
command-line-arguments

# go build 自定义可执行文件
go-in-action/chapter1/hello on  main [?] via 🐹 v1.15.7 at ☸️  yogo-dev (spf)
➜ go build -o main hello.go

go build 编译代码包顺序 [依赖代码包 -> 当前代码包 -> 触发代码包]
```

* go install
> 编译并安装制定的代码包以及依赖包
```
go install 命令只比 go build 命令多做安装编译后的记过文件到指定目录
go install 命令不支持针对库源码文件的安装操作
```

* go get
> 下载或更新制定代码包以及依赖包并进行编译和安装
```
go get 命令被叫做代码包远程导入
go get 命令所做的是从代码版本控制系统的远程草枯中检出/更新代码包并对其进行编译和安装

# 导入注释
package analyzer // import "hypermind.cn/talon/analyzer"

# 列出本地和远程仓库中记录的代码包和所有分支和标签
$ git show-ref
```

* go clean
> 执行go clean命令回删除掉执行其它命令时产生的一些文件和目录
```
➜ go clean -x hello.go
cd /Users/chyiyaqing/chyi/github/go-in-action/chapter1/hello
rm -f hello hello.exe hello.test hello.test.exe hello hello.exe
```
