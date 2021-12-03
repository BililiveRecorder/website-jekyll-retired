---
title: 录播姬 Docker 版
---

录播姬 Docker 版与一般命令行版完全一样  
<https://github.com/Bililive/BililiveRecorder/pkgs/container/bililiverecorder>  
支持 `amd64 (x86-64)`, `arm32 (arm/v7)`, `arm64 (arm64/v8)` 三种架构

用法示例：

```sh
docker pull ghcr.io/bililive/bililiverecorder:latest
```

关于 docker volume 请查看 docker 文档  
[https://docs.docker.com/storage/volumes/]

```sh
# 标准（使用配置文件）模式运行
# 注意传入录播姬的参数是文件夹的路径，而不是 config.json 配置文件的路径
docker run -d --name recorder -v /data/rec:/rec ghcr.io/bililive/bililiverecorder:latest run /rec

# 无配置文件模式运行
docker run -d --name recorder -v /data/rec:/rec ghcr.io/bililive/bililiverecorder:latest portable /rec 1 2 3 4 5

# 使用工具箱分析录播文件并以 json 格式输出到 stdout
docker run -it --rm -v /data/rec:/rec ghcr.io/bililive/bililiverecorder:latest tool analyze "/rec/recording.flv" --json
```
