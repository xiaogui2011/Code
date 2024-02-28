# macos install engine

brew reinstall docker

brew install --cask docker

brew uninstall docker

{% embed url="https://stackoverflow.com/questions/44084846/cannot-connect-to-the-docker-daemon-on-macos" %}

<mark style="color:red;">docker: Cannot connect to the Docker daemon at unix:///var/run/docker.sock. Is the docker daemon running?. See 'docker run --help'.</mark>

```
brew install --cask docker
```

> Because docker is a system-level package, you cannot install it using `brew install`, and must use `--cask` instead.