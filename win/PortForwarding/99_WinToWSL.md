# 1. Preparation
# 1.1. Checking the IP Address
Note: Prerequisite: The WSL IP address is 172.28.164.85

```PowerShell
wsl hostname -I
# Example output: 172.28.164.85 172.17.0.1
```

# 2. Port Forwarding
## 2.1. Setup port forwarding
Listen for inbound on Windows at 0.0.0.0:8000.
Forward to WSL at 172.28.164.85:8000.

```PowerShell
netsh interface portproxy add v4tov4 listenport=8000 listenaddress=0.0.0.0 connectport=8000 connectaddress=172.28.164.85
```

## 2.2. Check port forwarding

```PowerShell
netsh interface portproxy show all
```

## 2.3. Remove port forwarding
Remove the setting to listen on Windows' 0.0.0.0:8000.
The rule forwarding to WSL's 172.28.164.85:8000 will also be removed.

```PowerShell
netsh interface portproxy delete v4tov4 listenport=8000 listenaddress=0.0.0.0
```

# 3. Firewall
## 3.1. Add Firewall Rule
Add a rule to allow access to port 8000.

```PowerShell
New-NetFirewallRule -DisplayName "WSL Port 8000" -Direction Inbound -LocalPort 8000 -Protocol TCP -Action Allow
```

## 3.2. Check Firewall Settings
Check the firewall configuration. ex, check port 8000.

```PowerShell
Get-NetFirewallRule | Where-Object {$_.DisplayName -like "*8000*"} | Format-Table DisplayName, Enabled, Direction, Action
```


## 3.3. Delete the rule that allows access to port 8000
The permission rule “WSL Port 8000” has been deleted. This is not a denial of port 8000.

```PowerShell
Remove-NetFirewallRule -DisplayName "WSL Port 8000"
```