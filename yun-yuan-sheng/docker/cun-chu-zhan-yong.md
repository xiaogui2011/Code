---
description: docker
---

# 写满磁盘

## 检查分区

/mnt/registry/registry/docker/registry/v2/blobs/sha256

```bash
[root@harbor v2]# du -h --max-depth=1
183M	./repositories
42G	./blobs
42G	.
```

```sh
du -h --max-depth=1  | sort -hr
```

## 清理不必要的文件

目的: 释放一部分空间, 方便登录界面

```
find ./ "*.log" -type f -exec rm {} \;
```

```
find ./ -name "*.tmp" -type f -exec rm {} \;
```

```
find -name "cron.log" -type f -mtime +7 -exec rm {} \;
```

```
find ./ -size +100M -type f
```

## <mark style="background-color:red;">修改data\_volume</mark>

The default data volume

data\_volume: /mnt/registry
