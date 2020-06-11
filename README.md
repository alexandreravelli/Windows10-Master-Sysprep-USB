# LUSH - Windows 10 Master
Install Windows 10 on a new computer - LUSH


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

<?xml version="1.0" encoding="UTF-8"?>

-<unattend xmlns="urn:schemas-microsoft-com:unattend">


-<settings pass="windowsPE">


-<component language="neutral" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:wcm="http://schemas.microsoft.com/WMIConfig/2002/State" versionScope="nonSxS" publicKeyToken="31bf3856ad364e35" processorArchitecture="amd64" name="Microsoft-Windows-International-Core-WinPE">


-<SetupUILanguage>

<UILanguage>fr-FR</UILanguage>

</SetupUILanguage>

<SystemLocale>fr-FR</SystemLocale>

<UILanguage>fr-FR</UILanguage>

<UILanguageFallback>fr-FR</UILanguageFallback>

<UserLocale>fr-FR</UserLocale>

<InputLocale>040c:0000040c</InputLocale>

</component>


-<component language="neutral" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:wcm="http://schemas.microsoft.com/WMIConfig/2002/State" versionScope="nonSxS" publicKeyToken="31bf3856ad364e35" processorArchitecture="amd64" name="Microsoft-Windows-Setup">


-<UserData>


-<ProductKey>

<Key>VK7JG-NPHTM-C97JM-9MPGT-3V66T</Key>

<WillShowUI>Never</WillShowUI>

</ProductKey>

</UserData>

</component>

</settings>


-<settings pass="oobeSystem">


-<component language="neutral" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:wcm="http://schemas.microsoft.com/WMIConfig/2002/State" versionScope="nonSxS" publicKeyToken="31bf3856ad364e35" processorArchitecture="amd64" name="Microsoft-Windows-Shell-Setup">


-<UserAccounts>


-<LocalAccounts>


-<LocalAccount wcm:action="add">


-<Password>

<Value>bQBvAHQAZABlAHAAYQBzAHMAZQBQAGEAcwBzAHcAbwByAGQA</Value>

<PlainText>false</PlainText>

</Password>

<DisplayName>davlgd</DisplayName>

<Group>Administrators</Group>

<Name>davlgd</Name>

</LocalAccount>

</LocalAccounts>

</UserAccounts>

<TimeZone>Europe/Paris</TimeZone>


-<OOBE>

<HideEULAPage>true</HideEULAPage>

<ProtectYourPC>2</ProtectYourPC>

<HideWirelessSetupInOOBE>true</HideWirelessSetupInOOBE>

<HideOEMRegistrationScreen>true</HideOEMRegistrationScreen>

<HideOnlineAccountScreens>true</HideOnlineAccountScreens>

<UnattendEnableRetailDemo>false</UnattendEnableRetailDemo>

</OOBE>

</component>


-<component language="neutral" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:wcm="http://schemas.microsoft.com/WMIConfig/2002/State" versionScope="nonSxS" publicKeyToken="31bf3856ad364e35" processorArchitecture="amd64" name="Microsoft-Windows-International-Core">

<InputLocale>040c:0000040c</InputLocale>

<SystemLocale>fr-FR</SystemLocale>

<UILanguage>fr-FR</UILanguage>

<UILanguageFallback>fr-FR</UILanguageFallback>

<UserLocale>fr-FR</UserLocale>

</component>

</settings>

<cpi:offlineImage xmlns:cpi="urn:schemas-microsoft-com:cpi" cpi:source="wim:c:/users/benchs/desktop/test%20image/sources/install.wim#Windows 10 Pro"/>

</unattend>

- ``` sysprep.exe /oobe /generalize /unattend:unattend.xml /shutdown ```

