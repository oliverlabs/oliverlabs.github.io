---
title: 'Nifty Powershell Functions and Aliases'
date: '2024-01-22T09:07:02Z'
draft: false
tags:
- PowerShell
---

I thought I'd share some of the Powershell functions and aliases I've found useful over the years. I'll try to keep this updated as I find new ones.

# Powershell Aliases

```powershell
Set-Alias -Name "tf" -Value "terraform"
Set-Alias -Name k -Value kubectl
Set-Alias -Name tt -Value tree
Set-Alias -Name ll -Value ls
Set-Alias g git
Set-Alias vim nvim
Set-Alias -Name np -Value 'C:\Windows\notepad.exe'
Set-Alias -Name code -Value code-insiders
Set-Alias -Name npp -Value 'C:\Program Files\Notepad++\notepad++.exe'
Set-Alias -Name buildnumber -Value "Get-OSBuild"
```

# Powershell Functions

## Command History

I like having access to terminal history even after I close the terminal and reopen it later. So I wrote a function to do that. It uses PSReadLine plugin to query the history file and return the last 100 lines. I have this function aliased to `hist`.

```powershell
# This function gets a history of the last 100 commands from PSReadLine log file
function hist {
    gc (Get-PSReadLineOption).HistorySavePath -tail 100
}
```

## Open GitHub Repo in a Browser

I use this function to open the current directory in a browser directly from the command line. I have this aliased to `gh`.

```powershell
# This function opens a github repo in the browser
function gitopen {
    start (git config --get remote.origin.url)
}
```

## Find Executable Path

I use this function to find the path of an executable. It is nifty for finding the location of things like terraform or bicep. I have this aliased to `which`.

```powershell
# This function finds executables

function whereis ($command) {
    Get-Command -Name $command -ErrorAction SilentlyContinue |
    Select-Object -ExpandProperty Path -ErrorAction SilentlyContinue
}
```

## Create A New Directory And Change To It

I use this function to create a new directory and change to it with one short alias. I have this aliased to `mcd`.

```powershell
function mcd {
    param (
        [Parameter(Mandatory = $true)]
        [string]$folderName
    )

    New-Item -ItemType Directory -Force -Path $folderName
    Set-Location -Path $folderName
}
```

## Get OS Build Number

I am an active Windows Insider user, so I check my Windows build numbers frequently. I use this function to get the OS build number. I have this aliased to `Get-OSBuild`.

```powershell
function Get-OSBuild {
  (Get-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Windows NT\CurrentVersion" -Name BuildLabEx).BuildLabEx.Split(".")[0]
}
```

## Lazy Git Commit

I use this function to quickly commit changes to a git repo. I have this aliased to `acp`. ACP stands for Add, Commit, Push.

```powershell
## Lazy Git ACP Function
function acp($commitMessage) {
    git add .
    git commit -a -m $commitMessage
    git push
}
```