# snap
## case1
```
sudo mkdir -p /etc/systemd/system/snapd.service.d
sudo vim /etc/systemd/system/snapd.service.d/proxy.conf
```

```
[Service]
Environment="HTTP_PROXY=http://user:pass@ProxyIP:ProxyPort/"
Environment="HTTPS_PROXY=http://user:pass@ProxyIP:ProxyPort/"
Environment="NO_PROXY=localhost,127.0.0.1,HostNetwork,DockerNetwork"
```

## case2
```
sudo snap set system proxy.http="http://user:pass@ProxyIP:ProxyPort/"
sudo snap set system proxy.https="http://user:pass@ProxyIP:ProxyPort/"
```

## check
```
sudo snap get system proxy
```

```
snap find hello
```