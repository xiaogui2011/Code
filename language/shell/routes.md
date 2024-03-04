# routes

```sh
sudo ip route add 10.0.0.0/8   via 10.61.64.1
sudo ip route add 100.64.0.0/10 via 10.61.64.1
sudo ip route add 127.0.0.0/8 via 10.61.64.1
sudo ip route add 172.16.0.0/12 via 10.61.64.1
sudo ip route add 192.168.0.0/16 via 10.61.64.1
sudo ip route add 220.181.111.0/24 via 10.61.64.1
sudo ip route add 223.5.5.5/32  via 10.61.64.1


效果
0 zhang@zhang:/usr/local/bin$ route -n
内核 IP 路由表
目标            网关            子网掩码        标志  跃点   引用  使用 接口
0.0.0.0         192.168.0.1     0.0.0.0         UG    0      0        0 enp0s20f0u14
10.61.64.0      0.0.0.0         255.255.224.0   U     0      0        0 eno1
100.64.0.0      10.61.64.1      255.192.0.0     UG    0      0        0 eno1
127.0.0.0       10.61.64.1      255.0.0.0       UG    0      0        0 eno1
172.16.0.0      10.61.64.1      255.240.0.0     UG    0      0        0 eno1
192.168.0.0     10.61.64.1      255.255.0.0     UG    0      0        0 eno1
220.181.111.0   10.61.64.1      255.255.255.0   UG    0      0        0 eno1

```
