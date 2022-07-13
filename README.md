# S1_Remo_Shell_Windows_Triage

## Notes

most commands are powershell and will run as is, some however are cmd.exe commands and you will need to drop into cmd.exe, or append the call to cmd.exe before the command. (cmd.exe /c "#the_command_here")

Some commands output is easier to read by writing to a file and pulling the file to open in a text editor.

## System Information

Gets system Date and Time
```powershell
echo %DATE% %TIME%
```
Gets hostname
```powershell
hostname
```
Gathers some system info
```powershell
systeminfo
```
Gets logon server
```powershell
systeminfo | findstr "Logon Server"
```
Grabs domain logon server OS info
```powershell
systeminfo | findstr /B /C:"OS Name" /C:"OS Version" /C:"Domain" /C:"Logon Server"
```
Grabs "Domain     Manufacturer         Model                Name             PrimaryOwnerName      TotalPhysicalMemory" 
```powershell
wmic computersystem list brief
```
Lists installed products and their version
```powershell
wmic product get name,version
```
Lists current paths in scope
```powershell
cmd.exe /c "echo %PATH%"
```

## User Information
```powershell
whoami
```
```powershell
net users
```
```powershell
net localgroup administrators
```
Only works on domain controllers
```powershell
net group administrators
```
check rdp
```powershell
wmic rdtoggle list
```
List groups
```powershell
wmic group list
```
```powershell
wmic netlogin get name,lastlogon,badpasswordcount
```
```powershell
wmic netclient list brief
```
may not work unless history is turned on, or may have to figure out how to specify users
```powershell
doskey /history > history.txt
```

## Network Information - Open Connections etc

Gets total bytes sent and recieved
```powershell
netstat -e
```
gets all active connections, their status and pid.
```powershell
netstat -boan
```
gets routing information
```powershell
netstat -rn
```
```powershell
netstat -vb
```
```powershell
nbtstat -S
```
```powershell
route print
```
```powershell
arp -a
```
```powershell
ipconfig /displaydns
```
```powershell
netsh winhttp show proxy
```
```powershell
ipconfig /allcompartments /all
```
```powershell
netsh wlan show interfaces
```
```powershell
netsh wlan show all
```
```powershell
type %SYSTEMROOT%\system32\drivers\etc\hosts
```
```powershell
wmic nicconfig get descriptions,IPaddress,MACaddress
```
```powershell
wmic netuse get name,username,connectiontype,localname
```

## Services / Schtasks

```powershell
schtasks
```

```powershell
tasklist
```
```powershell
tasklist /svc
```
```powershell
tasklist /svc /fi "imagename eq svchost.exe"
```
```powershell
tasklist /svc /fi "pid eq <PID>"
```
```powershell
net start
```
```powershell
sc query
```
```powershell
wmic service list breif | findstr "Running"
```
```powershell
wmic service list config
```
```powershell
wmic process list brief
```
```powershell
wmic service list status
```
```powershell
wmic service list memory
```
```powershell
wmic job list brief
```
```powershell
Get-Service | where-Object { $_.Status -ep "running" }
```
```powershell
Get-Process | select modules | foreach-Object{$_.modules}
```
## Policy Patch Settings info
```powershell
cmd.exe /c "set"
```
```powershell
gpresult /r
```
```powershell
wmic qfe
```
## Autoruns / Autoloads
```powershell
wmic startup list full
```
```powershell
wmic startup list brief
```
```powershell
# need to drop into cmd.exe
dir "%SystemDrive%\Microsoft\Windows\Start Menu\Programs\StartUp"
```
```powershell
# need to drop into cmd.exe
dir "%SystemDrive%\Documents and Settings\All Users\Start Menu\Programs\Startup"
```
```powershell
# need to drop into cmd.exe
dir "%userprofile%\Start Menu\Programs\Startup"
```
```powershell
dir "C:\Windows\Start Menu\Programs\Startup"
```
```powershell

```
```powershell

```
```powershell

```
```powershell

```
```powershell

```
```powershell

```
