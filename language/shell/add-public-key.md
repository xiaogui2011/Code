# add-public-key

```sh
#!/bin/bash

name="$(whoami)"

path="$(getent passwd | cut -d: -f6 | grep $name)"

echo $path

# 当前用户的公钥的路径
rsaPub="${path}/.ssh/id_rsa.pub"

pubContent="$(cat $rsaPub)"

# https://superuser.com/questions/400714/how-to-remotely-write-to-a-file-using-ssh
echo $pubContent | ssh root@$1 -T "cat >> /root/.ssh/authorized_keys"

# TODO how to pretend to write multiple keys to remote server.
ssh root@$1
```

```sh
#!/bin/bash

name="$(whoami)"

path="$(getent passwd | cut -d: -f6 | grep $name)"

echo $path

# 当前用户的公钥的路径
rsaPub="${path}/.ssh/id_rsa.pub"

pubContent="$(cat $rsaPub)"

# https://superuser.com/questions/400714/how-to-remotely-write-to-a-file-using-ssh
echo $pubContent | ssh root@$1 -T "cat >> /root/.ssh/authorized_keys"

# TODO how to pretend to write multiple keys to remote server.
ssh root@$1

```
