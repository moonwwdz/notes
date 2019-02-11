# 快捷链接
[Tmux快捷键列表](https://gist.github.com/ryerh/14b7c24dfd623ef8edc7)
[乌云文章列表](https://wooyun.js.org/)
[FRP设置例子](https://www.xyzbeta.com/460)

# Golang

## 交差编译
在一个环境下，编译出其它系统上可用的二进制文件
```bash
# 如果你想在Windows 32位系统下运行
➜  ~CGO_ENABLED=0 GOOS=windows GOARCH=386 go build test.go

# 如果你想在Windows 64位系统下运行
➜  ~CGO_ENABLED=0 GOOS=windows GOARCH=amd64 go build test.go

# 如果你想在OS X 32位系统下运行
➜  ~CGO_ENABLED=0 GOOS=darwin GOARCH=386 go build test.go

# 如果你想在OS X 64位系统下运行
➜  ~CGO_ENABLED=0 GOOS=darwin GOARCH=amd64 go build test.go

# 如果你想在Linux 32位系统下运行
➜  ~CGO_ENABLED=0 GOOS=linux GOARCH=386 go build test.go

# 如果你想在Linux 64位系统下运行
➜  ~CGO_ENABLED=0 GOOS=linux GOARCH=amd64 go build test.go
```
