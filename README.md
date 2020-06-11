# LUSH - Windows 10 Master - Sysprep 
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

https://github.com/alexandreravelli/lush-windows10/blob/master/unattend.xml

Put unattend.xml to C:\Windows\System32\Sysprep

![7](https://user-images.githubusercontent.com/22911613/84355106-5669c980-abc2-11ea-97a2-74a4f6a6845a.jpg)

- ``` sysprep.exe /oobe /generalize /unattend:unattend.xml /shutdown ```

/// 4 - Dism ///

-VMware - Power On The Firmware 

![10](https://user-images.githubusercontent.com/22911613/84355474-f889b180-abc2-11ea-8a90-2c7ae33b6939.jpg)

- ``` dism /Capture-Image /Imagefile:C:\install.wim /CaptureDir:C:\ /Name:"Master-Windows-10" ```

![11](https://user-images.githubusercontent.com/22911613/84358253-2b35a900-abc7-11ea-8d9d-8e11cd809d94.jpg)


