# exporter

## MYSQL

### docker启动

```shell
docker run -d --name mysqld_exporter -p 9104:9104 -e DATA_SOURCE_NAME="root:JdZ6ym5uOH@(172.16.4.65:30682)/" prom/mysqld-exporter:v0.14.0
```

```shell
docker run -d --name mysqld_exporter -p 9104:9104 -e DATA_SOURCE_NAME="root:JdZ6ym5uOH@(192.168.10.151:32383)/" prom/mysqld-exporter:v0.14.0
```

### 二进制启动

```
./mysqld_exporter --config.my-cnf="/root/exporter/mysqld_exporter-0.15.1.linux-amd64/localhost_db.cnf" --web.listen-address=":9105"
```

```bash
0 14:58:34 192.168.10.241:~/exporter/mysqld_exporter-0.15.1.linux-amd64 $ tree
.
├── LICENSE
├── localhost_db.cnf
├── mysqld_exporter
└── NOTICE

0 directories, 4 files
0 14:58:36 192.168.10.241:~/exporter/mysqld_exporter-0.15.1.linux-amd64 $ cat localhost_db.cnf
[client]
user=root
password=111111
port=1111
host=192.168.10.233

0 14:58:39 192.168.10.241:~/exporter/mysqld_exporter-0.15.1.linux-amd64 $ ./mysqld_exporter --config.my-cnf="/root/exporter/mysqld_exporter-0.15.1.linux-amd64/localhost_db.cnf" --web.listen-address=":9105"
ts=2024-01-22T06:58:45.336Z caller=mysqld_exporter.go:220 level=info msg="Starting mysqld_exporter" version="(version=0.15.1, branch=HEAD, revision=cc349684494b5038ec5a52233bdca9eb9291e6f2)"
ts=2024-01-22T06:58:45.336Z caller=mysqld_exporter.go:221 level=info msg="Build context" build_context="(go=go1.21.5, platform=linux/amd64, user=root@d89c15b9f5ad, date=20231212-07:55:09, tags=unknown)"
ts=2024-01-22T06:58:45.336Z caller=mysqld_exporter.go:233 level=info msg="Scraper enabled" scraper=global_status
ts=2024-01-22T06:58:45.336Z caller=mysqld_exporter.go:233 level=info msg="Scraper enabled" scraper=global_variables
ts=2024-01-22T06:58:45.336Z caller=mysqld_exporter.go:233 level=info msg="Scraper enabled" scraper=slave_status
ts=2024-01-22T06:58:45.336Z caller=mysqld_exporter.go:233 level=info msg="Scraper enabled" scraper=info_schema.innodb_cmp
ts=2024-01-22T06:58:45.336Z caller=mysqld_exporter.go:233 level=info msg="Scraper enabled" scraper=info_schema.innodb_cmpmem
ts=2024-01-22T06:58:45.336Z caller=mysqld_exporter.go:233 level=info msg="Scraper enabled" scraper=info_schema.query_response_time
ts=2024-01-22T06:58:45.337Z caller=tls_config.go:274 level=info msg="Listening on" address=[::]:9105
ts=2024-01-22T06:58:45.337Z caller=tls_config.go:277 level=info msg="TLS is disabled." http2=false address=[::]:9105
```

## redis

### 二进制启动

```shell
./redis_exporter -redis.addr 192.168.10.151:32641 -redis.password  -web.listen-address 0.0.0.0:9121
```

```shell
0 15:49:35 192.168.10.241:/usr/local/wwmonitor/plugins/redis_exporter $ ps -ef | grep redis
root     53167     1  0  2023 ?        00:01:44 ./redis_exporter -redis.addr 192.168.10.151:32641 -redis.password  -web.listen-address 0.0.0.0:9121
root     59406 49033  0 15:49 pts/2    00:00:00 grep --color=auto redis
0 15:49:39 192.168.10.241:/usr/local/wwmonitor/plugins/redis_exporter $ kill -9 53167
0 15:49:46 192.168.10.241:/usr/local/wwmonitor/plugins/redis_exporter $ ./redis_exporter -redis.addr 192.168.10.151:32641 -redis.password  -web.listen-address 0.0.0.0:9121
INFO[0000] Redis Metrics Exporter v1.54.0    build date: 2023-09-05-21:56:29    sha1: 4df89bf3349009a8b145bf19fb086c775a6de1b9    Go: go1.20.7    GOOS: linux    GOARCH: amd64
INFO[0000] Providing metrics at :9121/metrics
```

### 二进制后台启动

```shell
#!/bin/bash

listen_address="0.0.0.0:9121"
nohup ./redis_exporter -redis.addr "192.168.10.151:32641" -redis.password "baKuTbjXAh"  -web.listen-address  "$listen_address" 1>/dev/null 2>&1 & echo $! > redis_exporter.pid
```

```shell
nohup /root/exporter/mysqld_exporter-0.15.1.linux-amd64/mysqld_exporter --config.my-cnf="/root/exporter/mysqld_exporter-0.15.1.linux-amd64/localhost_db.cnf" --web.listen-address=":9105" > /tmp/mysql_exporter.log 2>&1 &
```

## mongodb

### 二进制启动

```shell
/usr/local/wwmonitor/plugins/mongodb_exporter-0.40.0.linux-amd64/mongodb_exporter --mongodb.user=root --mongodb.password=txSeuiGXRg --mongodb.uri=mongodb://192.168.10.241:30446 --collector.profile --collector.collstats --mongodb.collstats-colls=db1.c1,db2.c2 --collect-all
```


## nginx

### 开启`ngx_http_stub_status_module`模块

```shell
0 15:34:35 192.168.10.151:~ $ cat /etc/nginx/nginx.conf
user  nginx;
worker_processes  1;

error_log  /var/log/nginx/error.log warn;
pid        /var/run/nginx.pid;

events {
    worker_connections  1024;
}


http {
    include       /etc/nginx/mime.types;
    default_type  application/octet-stream;

    log_format  main  '$remote_addr - $remote_user [$time_local] "$request" '
                      '$status $body_bytes_sent "$http_referer" '
                      '"$http_user_agent" "$http_x_forwarded_for"';

    access_log  /var/log/nginx/access.log  main;

    sendfile        on;
    #tcp_nopush     on;
    #tcp_nopush     on;

    keepalive_timeout  65;

    #gzip  on;

    # 启用 stub_status 模块，监听 8080 端口
    server {
        listen 8080;
        location /nginx_status {
            stub_status on;
            access_log off;
            allow 127.0.0.1;
            deny all;
        }
    }

    include /etc/nginx/conf.d/*.conf;
}
```


### 配置
```shell
./nginx-prometheus-exporter -nginx.scrape-uri http://127.0.0.1/nginx_status &
```


### 二进制启动
```shell
./nginx-prometheus-exporter -nginx.scrape-uri http://127.0.0.1/nginx_status &
./nginx-prometheus-exporter -nginx.scrape-uri http://192.168.10.233:30896 &
```