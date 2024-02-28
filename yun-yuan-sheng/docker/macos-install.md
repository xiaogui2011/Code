# macos  install

## orbstack

{% embed url="https://ddev.readthedocs.io/en/stable/users/install/docker-installation/#macos" %}

```
brew install orbstack
```

<mark style="color:red;">比官方的消耗的资源小</mark>

## Brew

brew reinstall docker

brew install --cask docker

brew uninstall docker

{% embed url="https://stackoverflow.com/questions/44084846/cannot-connect-to-the-docker-daemon-on-macos" %}

<mark style="color:red;">docker: Cannot connect to the Docker daemon at unix:///var/run/docker.sock. Is the docker daemon running?. See 'docker run --help'.</mark>

```
brew install --cask docker
```

> Because docker is a system-level package, you cannot install it using `brew install`, and must use `--cask` instead.



## Colima

[替代 docker-desktop，Colima 来了](https://www.bilibili.com/video/BV16L4y1G7bS/?spm\_id\_from=333.337.search-card.all.click\&vd\_source=31e016075d5dc418e05dd62618989320)

```
brew install colima
colima list
colima start
docker run xxx
colima stop
```



##
