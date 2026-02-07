# apt
```bash
sudo vim /etc/apt/apt.conf.d/80proxy
```

```bash
Acquire::http::Proxy "http://user:pass@ProxyIP:ProxyPort/";
Acquire::https::Proxy "http://user:pass@ProxyIP:ProxyPort/";
```
