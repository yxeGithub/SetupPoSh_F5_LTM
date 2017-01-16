# SetupPoSh_F5_LTM
Documentation and Setup (How-To) for Powershell and F5 Integration 
I created this repository to help people setup PowerShell to work with F5 LTM modules.

1.  Download the LTM-POSH-Rest module - https://github.com/joel74/POSH-LTM-Rest - Use the “Close or download button and download as zip.
2.  Copy the LTM-POSH-REST Folder into c:\Users\{username}\Documents\WindowsPowerShell\Modules    - Create the directory if you need to.
3.  Run power shell as an administrator - Windows Key - Right click - run as administrator
4.  Change into the Modules directory - cd c:\Users\{username}\Documents\WindowsPowerShell\Modules
5.  You need to unblock the files - dir F5-LTM -Recurse | Unblock-File or if you still have it as a zip right click it and select unblock and then unzip it.
6.  Install the module - from the powershell command prompt run= Import-Module F5-LTM
7.  $Secpasswd = Read-Host -Prompt "Enter password" -AsSecureString
8.  $mycreds = New-Object System.Management.Automation.PSCredential "admin", $secpasswd
9.  New-F5Session -LTMName 'bigip.company.com' -LTMCredentials $mycreds -Default
10. Test-Functionality -TestVirtualServer 'TestMe' -TestVirtualServerIP 172.16.1.12 -TestPool 'TestPool01' -PoolMember 192.168.0.211
11.  You should see taht it connected to your F5 and created a VS, Pool, and members, and deleted them.  If you get a bunch of Red text that is bad and it didnt work.


