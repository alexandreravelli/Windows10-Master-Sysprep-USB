# LUSH - Windows 10 Master
Windows 10 Sysprep - LUSH


**///  1 - Sysprep - Audit ///**
- ``` sysprep.exe /audit ```

![1](https://user-images.githubusercontent.com/22911613/84348777-1866a880-abb6-11ea-9856-f5bd5325f79c.jpg)

**///  2 - Install Multiple Softwares  ///**

![2](https://user-images.githubusercontent.com/22911613/84348996-a5116680-abb6-11ea-891e-e64e0c6cac97.jpg)

Choco

- ``` Set-ExecutionPolicy AllSigned ```
- ``` Set-ExecutionPolicy Bypass -Scope Process -Force; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1')) ```
- ``` choco install adobereader choco install googlechrome choco install 7zip.install choco install vlc choco install slack choco install bitwarden choco install google-backup-and-sync choco install spotify ```


Windows10debloater


**///  3 - Sysprep - oobe  ///**

- ``` sysprep.exe /oobe /generalize /unattend:unattend.xml /shutdown ```

