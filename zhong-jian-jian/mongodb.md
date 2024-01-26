# mongodb

mongodb.service

<mark style="background-color:orange;">--collect-all</mark>

<pre class="language-vim"><code class="lang-vim">[Unit]
Description=MongoDB Exporter

[Service]
ExecStart=/usr/local/wwmonitor/plugins/mongodb_exporter-0.40.0.linux-amd64/mongodb_exporter --mongodb.user=root --mongodb.password=txSeuiGXRg --mongodb.uri=mongodb://192.168.10.241:30446 --collector.profile --collector.collstats --mongodb.collstats-colls=db1.c1,db2.c2 <a data-footnote-ref href="#user-content-fn-1">--collect-all</a>
Restart=always
RestartSec=10

[Install]
WantedBy=default.target
</code></pre>



/usr/local/wwmonitor/conf/metrics.yml

```
-  dataid: 1200016
   enabled: true
   hosts:
     - http://192.168.10.241:9216/metrics
   module: prometheus
   metricsets:
     - collector
   namespace: mongodb_exporter
   period: 60
```

[^1]: 获取所有的指标
