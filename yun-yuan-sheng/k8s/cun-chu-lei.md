# 😀 存储类

## 概要

在 Kubernetes 中，<mark style="background-color:red;">存储类是一种抽象，它定义了动态存储的配置，包括存储的类型、属性和行为</mark>。

而物理磁盘则是实际存储数据的硬件设备，它们的关系可以通过存储类的配置来指定。



存储类的<mark style="color:red;">主要作用</mark>是为 PersistentVolumeClaim（PVC）提供动态的存储分配。

当用户创建一个 PVC，并指定了某个存储类，Kubernetes 就会根据存储类的配置，动态地创建一个 PersistentVolume（PV）来满足 PVC 的需求



当 PVC 使用某个存储类时，Kubernetes 将会根据存储类的配置将 PVC 绑定到相应的 PV，而 PV 可以映射到底层的物理磁盘。



这样，存储类提供了一个抽象层，使得用户可以方便地管理和使用存储，而不必关心底层的物理细节。



## <mark style="color:red;">创建NFS服务</mark>



## NFS使用

[mount nfs使用方法](https://blog.csdn.net/weixin\_41012399/article/details/120221702)

远程主机设置共享目录

```sh
# /配置文件
[root@localhost ~] cat /etc/exports
# 设置共享目录为/root, ，权限为可读，数据同步
/root 192.168.10.88(rw,sync,no_root_squash)

# /查看NFS共享列表
[root@localhost ~]#showmount -e 192.168.10.253
Export list for 192.168.10.253:
/root 192.168.10.88

# /挂载
# /mnt/nfs： 这是本地文件系统上用于挂载NFS共享目录的挂载点。
[root@localhost ~] mount -t nfs  192.168.10.253:/root/ /mnt/nfs/
[root@localhost ~] cd /mnt/nfs/
```

<mark style="color:red;">**showmount**</mark>**:**  The \`showmount\` command allows users to list available NFS shares on remote servers. This feature is vital for discovering and connecting to the resources you need.

<mark style="color:red;">**showmount:**</mark> 显示指定NFS服务器上的共享目录列表（或者叫输出列表）,要DNS能解析自己,意思就是可以看到NFS服务器共享出的哪些目录

<mark style="color:red;">exportfs</mark>命令： 用于管理NFS(Network File System)文件系统，在不直接编辑/etc/exports文件的情况下，可用exportfs来操作

<mark style="color:red;">mount</mark>：挂载到本地的某个文件夹下



## NFS的存储类

```yaml
apiVersion: storage.k8s.io/v1
kind: StorageClass
metadata:
  name: nfs-storage
provisioner: kubernetes.io/nfs
parameters:
  nfsServer: "nfs-server-ip-address"
  nfsPath: "/exported/path"
  
apiVersion: storage.k8s.io/v1
kind: StorageClass
metadata:
  name: nfs-storage
provisioner: kubernetes.io/no-provisioner
volumeBindingMode: WaitForFirstConsumer
allowVolumeExpansion: true
mountOptions:
  - vers=4
parameters:
  nfsServer: "192.168.10.253"
  nfsPath: "/root"
```
