# Windows 10 Master - Sysprep - USB 🦾

Prerequisite :

- Vmare Workstation 15.5 Pro
- Windows 10 ISO
- Rufus


**///  1 - Sysprep - Audit ///**

![5](https://user-images.githubusercontent.com/22911613/84352420-967a7d80-abbd-11ea-9540-a5a422b6fcbb.jpg)

- ``` sysprep.exe /audit ```

**///  2 - Install Multiple Softwares  ///**

![2](https://user-images.githubusercontent.com/22911613/84348996-a5116680-abb6-11ea-891e-e64e0c6cac97.jpg)

- Launch PowerShell - Choco

- ``` Set-ExecutionPolicy AllSigned ```
- ``` Set-ExecutionPolicy Bypass -Scope Process -Force; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1')) ```
- ``` choco install adobereader choco install googlechrome choco install 7zip.install choco install vlc choco install slack choco install bitwarden choco install google-backup-and-sync choco install spotify ```


**///  3 - Sysprep - oobe  ///**

![7](https://user-images.githubusercontent.com/22911613/84355106-5669c980-abc2-11ea-97a2-74a4f6a6845a.jpg)

<a class="github-button" href="https://github.com/alexandreravelli/Windows10-Master-Sysprep-USB/archive/master.zip" data-color-scheme="no-preference: dark; light: dark; dark: dark;" data-icon="octicon-download" data-size="large" aria-label="Download alexandreravelli/Windows10-Master-Sysprep-USB on GitHub">Download unattend.xml </a>

- Put unattend.xml to C:\Windows\System32\Sysprep

- ``` sysprep.exe /oobe /generalize /unattend:unattend.xml /shutdown ```

**/// 4 - Dism ///**

![10](https://user-images.githubusercontent.com/22911613/84355474-f889b180-abc2-11ea-8a90-2c7ae33b6939.jpg)

- VMware - Power On The Firmware 
- Shift f10 to open CMD
- Capture an Image Using DISM 

- ``` dism /Capture-Image /Imagefile:C:\install.wim /CaptureDir:C:\ /Name:"Master-Windows-10" ```

![11](https://user-images.githubusercontent.com/22911613/84358253-2b35a900-abc7-11ea-8d9d-8e11cd809d94.jpg)

 - .wim file location

![12](https://user-images.githubusercontent.com/22911613/84359154-84520c80-abc8-11ea-8e9f-4fb53ef5ddc9.jpg)

**/// 4 - Windows 10 To USB with .wim ///**

![13](https://user-images.githubusercontent.com/22911613/84360478-6be2f180-abca-11ea-96dc-21e30a98730a.jpg)

- Use RUFUS to copy windows10 ISO to USB - Format to NTFS
- If you select a Windows installation ISO, set the partition scheme to GPT partition scheme for UEFI computers and also set the file system to NTFS, Rufus will add everything required to allow booting NTFS partition from an UEFI system.

![12](https://user-images.githubusercontent.com/22911613/84361679-4ce55f00-abcc-11ea-8318-642d11987b65.jpg)

- Copy install.wim to your USB drive - E:\sources

**/// 5 - Put your USB to check the sysprep ///**

![13](https://user-images.githubusercontent.com/22911613/84367765-fcbeca80-abd4-11ea-8f4f-a8da0083c1ac.jpg)
![14](https://user-images.githubusercontent.com/22911613/84367777-00eae800-abd5-11ea-8b5d-48ee88691dad.jpg)
![15](https://user-images.githubusercontent.com/22911613/84367786-034d4200-abd5-11ea-8acc-f3b980ee37af.jpg)

