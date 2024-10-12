# Docker
## case1
```
sudo vim /etc/default/docker
```
```
export http_proxy="http://user:pass@ProxyIP:ProxyPort/"
export https_proxy="http://user:pass@ProxyIP:ProxyPort/"
export ftp_proxy="http://user:pass@ProxyIP:ProxyPort/"
export HTTP_PROXY="http://user:pass@ProxyIP:ProxyPort/"
export HTTPS_PROXY="http://user:pass@ProxyIP:ProxyPort/"
export FTP_PROXY="http://user:pass@ProxyIP:ProxyPort/"
export NO_PROXY="localhost,127.0.0.1"
export no_proxy="localhost,127.0.0.1"
```

## case2
```
sudo mkdir -p /etc/systemd/system/docker.service.d
sudo vim /etc/systemd/system/docker.service.d/override.conf
```

```
[Service]
Environment="HTTP_PROXY=http://user:pass@ProxyIP:ProxyPort/" "HTTPS_PROXY=http://user:pass@ProxyIP:ProxyPort/" "NO_PROXY=localhost,127.0.0.1"
```
