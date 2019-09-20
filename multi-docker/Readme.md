## docker多阶段构建
``
使用FROM ... AS ...语句
FROM golang：alpine AS builder
这一句就可以创建一个临时的builder镜像，并且还是像原来的Dockerfile命令一样操作这个容器。
FROM alpine
COPY --from=builder ....
这条COPY命令就可以从刚才临时构建的镜像里面把编译好的可执行文件拷贝到目标镜像里面，从而不用先创建一个image再COPY可执行文件到目标镜像
``
## docker 常见命令
- docker build --target stageName -t alexellis2/href-counter:latest .
