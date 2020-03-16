
# What I don't like

* install says it *might* not work unless run inside an administrator shell
  I would rather it detect when it needs to use the administrator shell to install a package and only require it then.  It would be even better if I could use a non-administrator shell and it could request temporary administrator access if it needs to perform a privileged operation.

* I'm not sure how to add a custom package/application to the chocolatey system.  For example, if I want to install an application that is not in the chocolatey register, but I want to be able to add it to my PATH using chocolatey's techniques/mechanisms, how would I do that?

# Install

* Start powershell as administrator

* Make sure `ExecutionPolicy` is unrestricted
```powershell
# Get current policy
Get-ExecutionPolicy

# If it returns "Restricted" then run one of these:
Set-ExecutionPolicy AllSigned
Set-ExecutionPolicy Bypass -Scope Process

# run Get-ExecutionPolicy again to verify it's no longer "Restricted"

```

* Run the install script

```powershell
Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))
```

> NOTE: you will probably need to reboot to complete install

# Common Usage

```
choco search <filter>
choco install <package-name>
```

# Packages that interest me

```
# for reading pdf files, snappier than chrome/IE
sumatrapdf

# I use the Calc (ExcelClone) program
# I can save in .fods format for git-friendly spreadsheet files
libreoffice
```
