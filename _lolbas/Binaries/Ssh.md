---
Name: ssh.exe
Description: Ssh.exe is the OpenSSH compatible client can be used to connect to Windows 10 (build 1809 and later) and Windows Server 2019 devices.
Author: 'Akshat Pradhan'
Created: '2021-11-08'
Commands:
  - Command: ssh localhost calc.exe
    Description: Execute calc.exe on host machine. The prompt for password can be eliminated by adding the host's public key in the user's authorized_keys file. Adversaries can do the same for execution on remote machines.
    Usecase: Execute specified command, can be used for defense evasion.
    Category: Execute
    Privileges: User
    MitreID: T1202
    OperatingSystem: Windows 10 1809, Windows Server 2019
  - Command: ssh -o ProxyCommand=calc.exe .
    Description: Executes calc.exe from ssh.exe
    Usecase: Performs execution of specified file, can be used as a defensive evasion.
    Category: Execute
    Privileges: User
    MitreID: T1202
    OperatingSystem: Windows 10
Full_Path:
  - Path: c:\windows\system32\OpenSSH\ssh.exe
Detection:
  - Sigma: https://github.com/SigmaHQ/sigma/blob/197615345b927682ab7ad7fa3c5f5bb2ed911eed/rules/windows/process_creation/proc_creation_win_lolbin_ssh.yml
  - IOC: Event ID 4624 with process name C:\Windows\System32\OpenSSH\sshd.exe.
  - IOC: command line arguments specifying execution.
Resources:
  - Link: https://gtfobins.github.io/gtfobins/ssh/
Acknowledgement:
  - Person: Akshat Pradhan
  - Person: Felix Boulet
---
