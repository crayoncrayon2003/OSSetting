# apt
```
sudo vim /etc/apt/apt.conf
```
```
Acquire::http::Proxy "http://user:pass@ProxyIP:ProxyPort/";
Acquire::https::Proxy "http://user:pass@ProxyIP:ProxyPort/";
```
