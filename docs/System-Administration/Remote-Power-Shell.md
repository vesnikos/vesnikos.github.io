
Remote `Powershell`-ing allows for a system administrator, to create a session from an existing powershell terminal to remotes host(s) and execute commands on it. 

## Host preparation

 Open a `Powershell` terminal as an `administrator` and enable it to accept remote connections:

```powershell title="Open Powershell as an administrator"
Enable-PSRemoting # (1)!
```

   1. The `Enable-PSRemoting` cmdlet performs the following operations:
       - Runs the Set-WSManQuickConfig cmdlet, which performs the following tasks:
           - **Starts** the WinRM service.  
           - Sets the startup type on the WinRM service to Automatic.  
           - Creates a listener to accept requests on any IP address.  
           -  Enables a firewall exception for WS-Management communications.  
           - Creates the simple and long name session endpoint configurations if needed.  
           - Enables all session configurations.  
           - Changes the security descriptor of all session configurations to allow remote access.  
       - Restarts the WinRM service to make the preceding changes effective.

1. fdsfdsqqqq

fdsfdsfdf

```powershell title="Verify the configurated endpoints"
Get-PSSessionConfiguration
```
```plaintext
Name          : PowerShell.7
PSVersion     : 7.4
StartupScript :
RunAsUser     :
Permission    : NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed, BUILTIN\Remote Management Users AccessAllowed

Name          : PowerShell.7.4.6
PSVersion     : 7.4
StartupScript :
RunAsUser     :
Permission    : NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed, BUILTIN\Remote Management Users AccessAllowed
```

!!! info "multiple powershell versions"
    Running `Enable-PSRemoting` will configure a remote endpoint for the specific version that you are running the cmdlet in. 
    
    So if you run `Enable-PSRemoting` while running PowerShell 5, a remoting endpoint will be configured that runs PowerShell 5. If you run Enable-PSRemoting while running PowerShell 7, a remoting endpoint will be configured that runs PowerShell 7 and so on.

    You can specify to which you want to connect to by using the `-ConfigurationName` parameter in the `Invoke-Command`,`New-PSSession`,`Enter-PSSession` cmdlets.  
    Chcck the configured endpoints with `Get-PSSessionConfiguration` as shown above.
 
