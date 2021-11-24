# WinRedOS

Run the following as admin with powershell. May need to do execution bypass. 

Note: enure you have creds set for the logged on user otherwise the main bit will fail. 

####Process (All in elevated powershell with bypass)
1. Install boxstarter. 

```powershell
. { Invoke-WebRequest -useb https://boxstarter.org/bootstrapper.ps1 } | iex; Get-Boxstarter -Force
```

2. Download the redwin_deploy.choco script using the boxstarter cmd prompt and run it as admin on the windows system using the prompted for credentials.
```powershell
$Cred = Get-Credential $env:USERNAME
Install-BoxstarterPackage -PackageName https://raw.githubusercontent.com/d-sec-net/winreddply/main/red_win_custom.choco -Credential $Cred 
#Dev version
#Install-BoxstarterPackage -PackageName https://raw.githubusercontent.com/grluk/WinRedOS/main/red_win_custom.choco -Credential $Cred 


```

### Docker issues
Ensure you enable CPU guest Virtualistaion if this build is to be run as a virtual guest. Otherwise you will get starting issues.
Note: You will need to install docker manually.
 
### misc
##### Error compiling in Visual Studio - Missing source packages
Compiling some projects error as there is a missing package, fix for the ones I've come across (grand total of 1!) is to update the nuget package sources with below:

Visual Studio > Tools >> Nuget Package Manager > Package Manager settings > (window pops up) Find Package Manager sources: Add below

        Name: nuget.org
        Source: https://api.nuget.org/v3/index.json


 
### Ready to roll!
All tools are in c:\tools, some will need to be compiled others should work out the box.

Keep an eye on that pesky Defender which will re-enable its self like a good AV should... the b4stard...

