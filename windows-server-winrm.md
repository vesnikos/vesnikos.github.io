---
tags:
 - windows/server-2022
---


Windows Remote Management, or winRM, is one component of the Windows Hardware Management features that manage server hardware locally and remotely. T


-- client 

Open group policies and navigate to Computer Configuration > Administrative Templates > Windows Components > Windows Remote Management (WinRM) > WinRM Client. 

Set: 
- Enable Basic authentication, 
- Enable CredSSP
- Enable Allow unencrypted traffic
- Enable Trusted Hosts
  - Add the IP address of the server you want to connect to or * for all servers.


To connect to a remote server using winRM, you can use the `Enter-PSSession` cmdlet. 

```powershell
Enter-PSSession blue -Authentication Negotiate -Credential dev\TestAdmin
```

Change `dev\TestAdmin` with the username and domain of the account you want to use to connect to the remote server.

The system will prompt you for the password of the account you provided.

```powershell
[blue]: PS C:\Users\TestAdmin\Documents>
```

### Configuration of winRM on the Server the client will connect to

- enable winRM
    the winRM service is not enabled by default on windows server
- configure the listener


At the target machine: 
To check the status of hte listener :
```powershell
winrm winrm get winrm/config
```


Quick default configuration
Enable the WS-Management protocol on the local computer, and set up the default configuration for remote management with the command:

```powershell
 winrm quickconfig
```


### Configure the client to use winRM

