# Docker Outbound Settings
## case1
```
sudo vim /etc/default/docker
```
```
export http_proxy="http://user:pass@ProxyIP:ProxyPort/"
export https_proxy="http://user:pass@ProxyIP:ProxyPort/"
export ftp_proxy="http://user:pass@ProxyIP:ProxyPort/"
export no_proxy="localhost,127.0.0.1,HostNetwork,DockerNetwork"

export HTTP_PROXY="http://user:pass@ProxyIP:ProxyPort/"
export HTTPS_PROXY="http://user:pass@ProxyIP:ProxyPort/"
export FTP_PROXY="http://user:pass@ProxyIP:ProxyPort/"
export NO_PROXY="localhost,127.0.0.1,HostNetwork,DockerNetwork"
```

## case2
```
sudo mkdir -p /etc/systemd/system/docker.service.d
sudo vim /etc/systemd/system/docker.service.d/override.conf
```

```
[Service]
Environment="HTTP_PROXY=http://user:pass@ProxyIP:ProxyPort/"
Environment="HTTPS_PROXY=http://user:pass@ProxyIP:ProxyPort/"
Environment="NO_PROXY=localhost,127.0.0.1,HostNetwork,DockerNetwork"
```

## case3
```
sudo vim ~/.docker/config.json
```

```
{
  "proxies": {
    "default": {
      "httpProxy": "http://user:pass@ProxyIP:ProxyPort/",
      "httpsProxy": "http://user:pass@ProxyIP:ProxyPort/",
      "noProxy": "localhost,127.0.0.1,HostNetwork,DockerNetwork"
    }
  }
}
```

# Docker Inbound Settings
[ref](https://github.com/crayoncrayon2003/OSSetting/tree/main/win/21_docker.md)

# Docker Network  Settings
Change the network address of the Docker network.
This setting is used to avoid conflicts with the host network.

Create daemon.json
```
mkdir ~/.docker
sudo vim /etc/docker/daemon.json
```

Add the following
```
{
    ...
    "bip": "192.20.0.254/24"
    ...
}
```

If this setting is used, it is recommended to align the network address in the docker-compose.yml as well.
This is because if the network address conflicts in the docker-compose.yml file, the setting will lose its effect.