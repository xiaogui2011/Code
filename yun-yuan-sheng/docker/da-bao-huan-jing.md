# 打包环境

```sh
docker run -id --name=golang -v /Users/zhangzhiyuan/go/ai-monitor-data:/root/ai-monitor-data  golang:1.20-alpine
docker ps
docker exec -it golang /bin/sh
```

通过ide进行代码编写

通过volume进行docker内部映射
