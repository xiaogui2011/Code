# ping

执行一次简单的IP地址范围的网络ping扫描

```sh
#!/bin/bash
echo "start"
for i in {1..254};do
        ip="202.100.86.$i"
        # 超时为1秒 -W 1
        ping -c 1 -W 1 $ip &> /dev/null && echo $ip is up &
        pids[${i}]=$!
done


# wait for all pids
for pid in ${pids[*]}; do
    wait $pid
done
echo "end"
```
