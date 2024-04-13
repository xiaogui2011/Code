# k8s

##

## HostPath

### pod内部文件挂载到宿主机

方便外边修改内部生效

```
apiVersion: v1
kind: Pod
metadata:
  name: nginx-pod
spec:
  containers:
  - name: nginx-container
    image: nginx:latest
    volumeMounts:
    - name: nginx-config
      mountPath: /etc/nginx/nginx.conf
      subPath: nginx.conf
volumes:
- name: nginx-config
  hostPath:
    path: /root/nginx.conf

```
