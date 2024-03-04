# routes-delete

```sh
route del -net 10.61.64.0 netmask 255.255.224.0
route del -net 172.17.0.0 netmask 255.255.0.0
route del -net 192.168.0.0 netmask 255.255.255.0

# ip route del 220.181.111.0
# ip route del 10.0.0.0
# ip route del 172.16.0.0
# ip route del 127.0.0.0
# ip route del 100.64.0.0

# route del -net 100.64.0.0 gw 10.61.64.1 netmask 255.192.0.0 dev eno1
# route del -net 172.16.0.0 gw 10.61.64.1 netmask 255.240.0.0 dev eno1
# route del -net 127.0.0.0 gw 10.61.64.1 netmask 255.192.0.0 dev eno1
# route del -net 172.16.0.0 gw 10.61.64.1 netmask 255.240.0.0 dev eno1

# route del -net 172.16.0.0/12 gw 10.61.64.1 dev eno1
# 
# route del -net 10.0.0.0  gw 10.61.64.1  netmask 255.0.0.0 dev eno1
# 
# sudo route del default gw 10.61.64.1
# 
# sudo route del -net 192.168.0.0 netmask 255.255.255.0

```
