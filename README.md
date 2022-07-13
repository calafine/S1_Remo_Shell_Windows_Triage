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
```powershell
net group administrators
```
```powershell
wmic rdtoggle list
```
```powershell
wmic group list
```
```powershell
wmic netlogin get name,lastlogon,badpasswordcount
```
```powershell
wmic netclient list brief
```
```powershell
doskey /history > history.txt
```

## Network Information - Open Connections etc

```powershell
netstat -e
```
```powershell
netstat -boan
```
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
arp -a

ipconfig /displaydns

netsh winhttp show proxy

ipconfig /allcompartments /all

netsh wlan show interfaces

netsh wlan show all

type %SYSTEMROOT%\system32\drivers\etc\hosts

wmic nicconfig get descriptions,IPaddress,MACaddress

wmic netuse get name,username,connectiontype,localname
```
