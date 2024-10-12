Authentication Proxy Setting

# Network Setting
step1. Click on the Start menu and select "Settings."
step2. In the Settings menu, select "Network & Internet."
step3. From the left-hand menu, choose "Proxy."
step4. Toggle the switch to "On" to enable the proxy server.
step5. settings
* Proxy IP Address      : any
* Proxy Port            : any
* Proxy Exceptions      : any
* Don't Use Proxy Server for Local Addresses: OFF

# System Environment Variables:
step1. Click on the Start menu and select "Settings."
step2. In the Settings menu, select "System."
step3. Click on "About" from the left-hand menu.
step4. Click the "Environment Variables" button.
step5. You'll see a list of system variables. To add a new one, click the "New" button.

## HTTP
* Name  ：http_proxy
* Value ：http://user:pass@ProxyIP:ProxyPort/
## HTTPS
* Name  ：http_proxy
* Value ：http://user:pass@ProxyIP:ProxyPort/
## HTTPS
* Name  ：no_proxy
* Value ：any

# PowerShell
Search for "PowerShell" in the Start menu and open it.
```
PS C:\dev> $env:http_proxy="http://user:pass@ProxyIP:ProxyPort/"
PS C:\dev> $env:https_proxy="http://user:pass@ProxyIP:ProxyPort/"
```

heck your proxy settings
```
PS C:\dev> get-childitem env:http_proxy
PS C:\dev> get-childitem env:https_proxy
```