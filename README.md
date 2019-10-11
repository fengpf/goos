## go os 调试过程

### go源码编译
```
$ https://github.com/fengpf/goos.git
$ cd go1.10.1/src

$ GOROOT_BOOTSTRAP=./ GO_GCFLAGS="-N -l" ./make.bash
```


### 设置 GOPATH & GOROOT

```
$ export GOROOT=/data/app/go/src/goos/go1.10.1
$ export GOBIN=$GOROOT/bin
$ export GOPATH=/data/app/go/src/goos
```


### 系统启动
```
$ cd ../biscuit
$ GOPATH=$(pwd) make qemu CPUS=2
```


### qemu 启动报错
qemu-system-x86_64: cannot set up guest memory 'pc.ram': Cannot allocate memory

处理办法: 分配的内存大于实际的内存，重新分配小一点的内存便可

