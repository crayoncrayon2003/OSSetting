# npm
```bash
npm config -g set proxy http://user:pass@ProxyIP:ProxyPort/
npm config -g set http-proxy http://user:pass@ProxyIP:ProxyPort/
npm config -g set https-proxy http://user:pass@ProxyIP:ProxyPort/
npm config -g set registry https://registry.npmjs.com/
npm config -g set strict-ssl false
```

`strict-ssl false` disables SSL certificate verification.
Use this setting only in environments where the proxy server performs SSL inspection.



check your proxy settings
```bash
npm config list
```