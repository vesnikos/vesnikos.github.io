---
tags:
 - windows/server
 - windows/server-2022
---

WinGet is a command line package manager for Windows; developed by microsoft. The tool allows you to install software pacakges from various sources.



## Windows Server

To enable it: 

1. Open a PowerShell terminal as an `administrator` and run:

``` powershell
C:\Users\Administrator> Install-Script winget-install
```

??? note "About winget-install"
    [winget-install](http://bit.ly/winget-install) is a PSGallery registered script that will download and install winget on your system. 


You should be able to use it to install software packages from the command line now. 

```powershell
PS C:\Users\Administrator> winget install -e --id Microsoft.WindowsTerminal
```

??? info "Windows Server 2025"
    `winget` is included in Windows Server 2025 by default.

## How to use
### Installing software
Let's install Windows Terminal with `winget`:

1. Find the package name:
```powershell
winget search -"Windows Terminal"

Name                     Id                                Version     Source
-------------------------------------------------------------------------------
Windows Terminal         9N0DX20HK701                      Unknown     msstore
Windows Terminal Preview 9N8G5RFZ9XK3                      Unknown     msstore
Windows Terminal         Microsoft.WindowsTerminal         1.21.3231.0 winget
Windows Terminal Preview Microsoft.WindowsTerminal.Preview 1.22.3232.0 winget
```

2. Install the package:
```powershel
winget install --id Microsoft.WindowsTerminal
```

### Keeping software up-to-date

To update all installed packages, run:

```powershell
winget upgrade --all 
```

??? note annotate "Administartor rights"
    If you're on windows 11 24H2 version or higher, you can run the above command with `sudo` to avoid any UAC prompts.


    If you are on an older version of windows, you can install `gsudo`(1) to achieve the same effect.
1. winget install --id gerardog.gsudo