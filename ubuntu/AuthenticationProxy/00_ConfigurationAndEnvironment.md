AuthenticationProxySetting

# Temporary proxy settings
```
export http_proxy=http://user:pass@ProxyIP:ProxyPort/
export https_proxy=http://user:pass@ProxyIP:ProxyPort/
sudo -E apt update
```

# Configuration
```
sudo vim ~/.bashrc
```

```
export http_proxy=http://user:pass@ProxyIP:ProxyPort/
export https_proxy=http://user:pass@ProxyIP:ProxyPort/
export ftp_proxy=http://user:pass@ProxyIP:ProxyPort/
export no_proxy=localhost,127.0.0.1
```

# Environment
```
sudo vim /etc/profile.d/proxy.sh
```

```
export http_proxy=http://user:pass@ProxyIP:ProxyPort/
export https_proxy=http://user:pass@ProxyIP:ProxyPort/
export ftp_proxy=http://user:pass@ProxyIP:ProxyPort/
export no_proxy=localhost,127.0.0.1
```
