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
That's why both uppercase and lowercase letters are included.
There is a tool that distinguishes between them.
```
export http_proxy=http://user:pass@ProxyIP:ProxyPort/
export https_proxy=http://user:pass@ProxyIP:ProxyPort/
export ftp_proxy=http://user:pass@ProxyIP:ProxyPort/
export no_proxy=localhost,127.0.0.1

export HTTP_PROXY=http://user:pass@ProxyIP:ProxyPort/
export HTTPS_PROXY=http://user:pass@ProxyIP:ProxyPort/
export FTP_PROXY=http://user:pass@ProxyIP:ProxyPort/
export NO_PROXY=localhost,127.0.0.1
```

# Environment
```
sudo vim /etc/profile.d/proxy.sh
```

That's why both uppercase and lowercase letters are included.
There is a tool that distinguishes between them.
```
export http_proxy=http://user:pass@ProxyIP:ProxyPort/
export https_proxy=http://user:pass@ProxyIP:ProxyPort/
export ftp_proxy=http://user:pass@ProxyIP:ProxyPort/
export no_proxy=localhost,127.0.0.1

export HTTP_PROXY=http://user:pass@ProxyIP:ProxyPort/
export HTTPS_PROXY=http://user:pass@ProxyIP:ProxyPort/
export FTP_PROXY=http://user:pass@ProxyIP:ProxyPort/
export NO_PROXY=localhost,127.0.0.1
```
