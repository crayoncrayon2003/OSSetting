# Docker
## case1
```
sudo vim /etc/default/docker
```
```
export http_proxy="http://user:pass@ProxyIP:ProxyPort/"
export https_proxy="http://user:pass@ProxyIP:ProxyPort/"
export ftp_proxy="http://user:pass@ProxyIP:ProxyPort/"
export no_proxy="localhost,127.0.0.1"

export HTTP_PROXY="http://user:pass@ProxyIP:ProxyPort/"
export HTTPS_PROXY="http://user:pass@ProxyIP:ProxyPort/"
export FTP_PROXY="http://user:pass@ProxyIP:ProxyPort/"
export NO_PROXY="localhost,127.0.0.1"
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
Environment="NO_PROXY=localhost,127.0.0.1"
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
      "noProxy": "localhost,127.0.0.1"
    }
  }
}
```

# Docker Network
Change the network address of the Docker network

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