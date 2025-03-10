---
Name: Provlaunch.exe
Description: Launcher process
Author: Grzegorz Tworek
Created: 2023-06-30
Commands:
  - Command: provlaunch.exe LOLBin
    Description: 'Executes command defined in the Registry. Requires 3 levels of the key structure containing some keywords. Such keys may be created with two reg.exe commands, e.g. "reg.exe add HKLM\SOFTWARE\Microsoft\Provisioning\Commands\LOLBin\dummy1 /v altitude /t REG_DWORD /d 0" and "reg add HKLM\SOFTWARE\Microsoft\Provisioning\Commands\LOLBin\dummy1\dummy2 /v Commandline /d calc.exe". Registry keys are deleted after successful execution.'
    Usecase: Executes arbitrary command
    Category: Execute
    Privileges: Administrator
    MitreID: T1218
    OperatingSystem: Windows 10, Windows 11, Windows Server 2012, Windows Server 2016, Windows Server 2019, Windows Server 2022
Full_Path:
  - Path: c:\windows\system32\provlaunch.exe
Detection:
  - IOC: c:\windows\system32\provlaunch.exe executions
  - IOC: Creation/existence of HKLM\SOFTWARE\Microsoft\Provisioning\Commands subkeys
Resources:
  - Link: https://twitter.com/0gtweet/status/1674399582162153472
Acknowledgement:
  - Person: Grzegorz Tworek
    Handle: '@0gtweet'
---
