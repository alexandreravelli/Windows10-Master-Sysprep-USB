# LUSH - Windows 10 Master
Windows 10 Sysprep - LUSH


**///  1 - Sysprep - Audit ///**
- ``` sysprep.exe /audit ```

![5](https://user-images.githubusercontent.com/22911613/84352420-967a7d80-abbd-11ea-9540-a5a422b6fcbb.jpg)

**///  2 - Install Multiple Softwares  ///**

![2](https://user-images.githubusercontent.com/22911613/84348996-a5116680-abb6-11ea-891e-e64e0c6cac97.jpg)

Launch PowerShell - Choco

- ``` Set-ExecutionPolicy AllSigned ```
- ``` Set-ExecutionPolicy Bypass -Scope Process -Force; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1')) ```
- ``` choco install adobereader choco install googlechrome choco install 7zip.install choco install vlc choco install slack choco install bitwarden choco install google-backup-and-sync choco install spotify ```


**///  3 - Sysprep - oobe  ///**

https://github.com/alexandreravelli/lush-windows10/blob/master/unattended.xml

- ``` sysprep.exe /oobe /generalize /unattend:unattend.xml /shutdown ```

