# windply

Run the following as admin with powershell.

Install boxstarter.

```powershell
. { Invoke-WebRequest -useb https://boxstarter.org/bootstrapper.ps1 } | iex; Get-Boxstarter -Force
```

Download the redwin_deploy.choco script using the boxstarter cmd prompy and run it as admin on the windows system using the prompted for credentials. 
```powershell
$Cred = Get-Credential $env:USERNAME
Install-BoxstarterPackage -PackageName https://raw.githubusercontent.com/dmaristi/windply/main/dply/redwin_deploy.choco -Credential $Cred 
```
