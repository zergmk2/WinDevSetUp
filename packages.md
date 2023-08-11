* It’s a oneliner that loops the installed Chocolatey apps via the “choco list” command and generates a list of strings.

```powershell
choco list -lo -r -y | % { "choco install $($_.SubString(0, $_.IndexOf("|"))) -y" } | Out-File Install.ps1

