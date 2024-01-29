# elasticsearch

## 启动elasticsearch\_exporter

{% code title="" overflow="wrap" lineNumbers="true" %}
```bash
nohup /root/exporter/es/elasticsearch_exporter/elasticsearch_exporter --es.all --es.indices --es.indices_settings --es.shards --es.timeout=10s --web.listen-address=":9115" --web.telemetry-path="/metrics" --es.uri http://192.168.10.241:30272 > exporter.log 2>&1 &
```
{% endcode %}
