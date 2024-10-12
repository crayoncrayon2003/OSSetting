# node
Don't use "sudo"

```
npm config -g set proxy http://user:pass@ProxyIP:ProxyPort/
npm config -g set http-proxy http://user:pass@ProxyIP:ProxyPort/
npm config -g set https-proxy http://user:pass@ProxyIP:ProxyPort/
npm config -g set registry http://registry.npmjs.com/
npm config -g set strict-ssl false
```

check your proxy settings
```
npm config list
```