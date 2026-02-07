# Docker Outbound Settings
## case1
```bash
sudo mkdir -p /etc/systemd/system/docker.service.d
sudo vim /etc/systemd/system/docker.service.d/http-proxy.conf
```

```ini
[Service]
Environment="HTTP_PROXY=http://user:pass@ProxyIP:ProxyPort/"
Environment="HTTPS_PROXY=http://user:pass@ProxyIP:ProxyPort/"
Environment="NO_PROXY=localhost,127.0.0.1,HostNetwork,DockerNetwork"
```

## case2
```bash
mkdir -p ~/.docker
vim ~/.docker/config.json
```

```json
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
[https://github.com/crayoncrayon2003/OSSetting/blob/main/win/AuthenticationProxy/21_docker.md](https://github.com/crayoncrayon2003/OSSetting/blob/main/win/AuthenticationProxy/21_docker.md)

# Docker Network  Settings
Change the network address of the Docker network.
This setting is used to avoid conflicts with the host network.

Create daemon.json
```bash
sudo mkdir -p /etc/docker
sudo vim /etc/docker/daemon.json
```

Add the following
```json
{
    ...
    "bip": "192.20.0.254/24"
    ...
}
```

If this setting is used, it is recommended to align the network address in the docker-compose.yml as well.
This is because if the network address conflicts in the docker-compose.yml file, the setting will lose its effect.