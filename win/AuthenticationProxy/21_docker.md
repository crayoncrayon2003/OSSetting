# Docker Outbound Settings
[https://github.com/crayoncrayon2003/OSSetting/blob/main/ubuntu/AuthenticationProxy/21_docker.md](https://github.com/crayoncrayon2003/OSSetting/blob/main/ubuntu/AuthenticationProxy/21_docker.md)

# Docker Inbound Settings
## Step1
1. Press Win + R.
2. Enter wf.msc.
3. Click “Inbound Rules.”
4. In the right-hand menu, click “New Rule…”
5. Select Port.
6. Specify the inbound port.
7. Select Allow the connection.
8. Check Domain / Private / Public.
9. Name the rule and save it.


## Step2
1. Open PowerShell with administrator privileges.
2. Enter the following command.
```
PS C:\Windows\System32> netsh interface portproxy add v4tov4 listenport=<Listen Port Number> listenaddress=<Listen IP Address> connectport=<Connect Port Number> connectaddress=<Connect IP Address>
```

| Parameter           | Description                                                                          |
| :------------------ | :----------------------------------------------------------------------------------- |
| Listen IP Address   | The IP address on the Windows OS that listens for connections from external systems  |
| Listen Port Number  | The port number on the Windows OS that listens for connections from external systems |
| Connect IP Address  | The destination IP address to which traffic is forwarded                             |
| Connect Port Number | The destination port number to which traffic is forwarded                            |
