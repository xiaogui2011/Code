# Colima

{% embed url="https://ddev.readthedocs.io/en/stable/users/install/docker-installation/" %}



{% embed url="https://juejin.cn/post/7223045442892234812" %}

```sh
 brew install colima
 brew install docker
 colima start --runtime containerd
```





{% embed url="https://linux.cn/article-15084-1.html" %}

> Colima 要求安装 Docker 或 [Podman](https://opensource.com/article/22/2/start-running-containers) 命令。在 Linux 上，它还需要 Lima。





{% embed url="https://blog.csdn.net/hello123yy/article/details/133935231" %}

> macOS 版Docker Desktop的性能问题也是让广大用户诟病
>
> <mark style="color:red;">colima 实际上是通过 Lima 启动了名为 colima 的虚拟机.</mark>

```
brew install docker
brew install docker-compose
brew install colima
```





{% embed url="https://blog.csdn.net/weiwoyonzhe/article/details/130173584?spm=1001.2101.3001.6650.7&utm_medium=distribute.pc_relevant.none-task-blog-2%7Edefault%7EBlogCommendFromBaidu%7ERate-7-130173584-blog-133935231.235%5Ev43%5Epc_blog_bottom_relevance_base9&depth_1-utm_source=distribute.pc_relevant.none-task-blog-2%7Edefault%7EBlogCommendFromBaidu%7ERate-7-130173584-blog-133935231.235%5Ev43%5Epc_blog_bottom_relevance_base9&utm_relevant_index=12" %}

> Intel and M1 Macs support

```sh
# 启动colima
# 注意，如果您不指定-e选项，则Colima将使用默认的配置文件。
# 默认情况下，Colima使用名为colima.yaml的配置文件，位于~/.colima//default/colima.yaml目录下。
colima start -e
```



