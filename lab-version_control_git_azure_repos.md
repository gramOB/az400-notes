# az400 microsoft learn lab: Version Control with Git in Azure Repos

```
https://microsoftlearning.github.io/AZ400-DesigningandImplementingMicrosoftDevOpsSolutions/Instructions/Labs/AZ400_M01_L02_Version_Control_with_Git_in_Azure_Repos.html
```

install git with winget

```
winget install --id Git.Git -e --source winget

```

install powershell 7 via winget

```
winget install --id Microsoft.PowerShell.Preview --source winget
# check path
$env:Path
```

configure credential helper

```
git config --global credential.helper wincred
```
