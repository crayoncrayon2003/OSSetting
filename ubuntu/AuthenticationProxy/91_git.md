# git
## case1
```bash
git config --global http.proxy http://user:pass@ProxyIP:ProxyPort/
git config --global https.proxy http://user:pass@ProxyIP:ProxyPort/
```

check your proxy settings
```bash
git config --global --list
```

## case2
```bash
vim ~/.gitconfig
```

```ini
[http]
    proxy = http://user:pass@ProxyIP:ProxyPort/
[https]
    proxy = http://user:pass@ProxyIP:ProxyPort/
```

check your proxy settings
```bash
cat ~/.gitconfig
```

## case3
Temporarily exclude proxy settings
```bash
git clone -c http.proxy="" http://XXXX.git
```