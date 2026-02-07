# pip
```bash
mkdir -p ~/.pip/
vim ~/.pip/pip.conf
```

```ini
[global]
proxy=http://user:pass@ProxyIP:ProxyPort/

[install]
trusted-host=pypi.org pypi.python.org files.pythonhosted.org
```
