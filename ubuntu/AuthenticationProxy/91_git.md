# git
## case1
```
git config --global http.proxy http://user:pass@ProxyIP:ProxyPort/
git config --global https.proxy http://user:pass@ProxyIP:ProxyPort/
```

check your proxy settings
```
git config --global --list
```

## case2
```
sudo vim ~/.gitconfig
```

```
[http]
    proxy = http://user:pass@ProxyIP:ProxyPort/
[https]
    proxy = http://user:pass@ProxyIP:ProxyPort/
```

check your proxy settings
```
cat ~/.gitconfig
```

## case3
Temporarily exclude proxy settings
```
git clone -c http.proxy="" http://XXXX.git
```