
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
