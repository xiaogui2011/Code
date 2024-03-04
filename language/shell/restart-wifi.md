---
description: ubuntu
---

# restart wifi

```
#!/bin/sh
ifconfig enp0s20f0u14 down
ifconfig enp0s20f0u13 down
echo "downed"
ifconfig enp0s20f0u14 up
ifconfig enp0s20f0u13 up
echo "uped"
dhclient enp0s20f0u14
dhclient enp0s20f0u13
echo "cliented"

route del default gw 10.61.64.1
sleep 1

route add default gw 192.168.0.1
sleep 1






```
