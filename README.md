# windply

Run the following as admin with powershell.

Install boxstarter.

```powershell
. { Invoke-WebRequest -useb https://boxstarter.org/bootstrapper.ps1 } | iex; Get-Boxstarter -Force
```

Download the redwin_deploy.choco script using the boxstarter cmd prompt and run it as admin on the windows system using the prompted for credentials. 
```powershell
$Cred = Get-Credential $env:USERNAME
Install-BoxstarterPackage -PackageName https://raw.githubusercontent.com/d-sec-net/winreddply/main/red_win_custom.choco -Credential $Cred 
```

### Docker issues
Ensure you enable CPU guest Virtualistaion if this build is to be run as a virtual guest. Otherwise you will get starting issues.
 
### Ready to roll!
All tools are in c:\tools, some will need to be compiled others should work out the box.
Keep an eye on that pesky Defender which will re-enable its self like a good AV should... the b4stard...
