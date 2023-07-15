# **Tutorial on how to install WSL in Windows 10**

## What is?

__WSL is the Windows Subsystem for Linux, which allows running a Linux (GNU/Linux) environment, including most command line tools, directly on Windows, without modifications and without the overhead of a virtual machine or DualBoot.__

## Installing
[Microsoft Learn](https://learn.microsoft.com/en-us/windows/wsl/install-manual)

## Step 1 - Enable the **Windows Subsystem for Linux**

__Open PowerShell as Administrator__
__Paste this code:__
>PowerShell
```bash
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
```

## Step 2 - Check requirements for running **WSL 2**

For **x64** systems: __Version 1903 or later, with Build 18362.1049 or later.__
For **ARM64** systems: __Version 2004 or later, with Build 19041 or later.__

## Step 3 - Enable **Virtual Machine** feature

>PowerShell
```bash
dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
```

## Step 4 - Download the **Linux** kernel update package
>Install
For **x64** systems: https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi
For **ARM64** systems: https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_arm64.msi

If there is an error and you are unable to install, follow these steps

Start -> Control panel -> Programs -> Turn Windows features on or off

Virtual Machine Platform and Windows Subsystem for Linux

If checked, uncheck both -> OK -> Restart your computer

Start -> Control panel -> Programs -> Turn Windows features on or off
Check Virtual Machine Platform and Windows Subsystem for Linux -> OK -> Restart your computer

Try to install again

## Step 5 - Set **WSL 2** as your **default** version
>PowerShell
```bash
wsl --set-default-version 2
```

## Step 6 - Install your **Linux** distribution of choices

Start -> Microsoft Store -> Search -> type Linux -> Enter

Select your favorite Linux distribution
> __I Recommend Ubunto 20.04 LTS__
Install -> Open -> Set **Username** and **Password**

## Step 7 - Install Windows Terminal (optional)

__Windows Terminal allows you to work in a more flexible and integrated way with Windows__

Start -> Microsoft Store -> type Windows Terminal -> install
Open **Windows Terminal** -> dropdown button -> settings -> Default Profile -> select **Ubunto 20.04 LTS**

## Step 8 - Test the terminal
> Windows Terminal
```bash
cd ~
cd /mnt/c/Users/your_username
```

Install **Remote WSL** extension in **VScode**