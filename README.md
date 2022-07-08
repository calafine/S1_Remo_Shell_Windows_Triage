# S1_Remo_Shell_Windows_Triage

## Notes

most commands are powershell and will run as is, some however are cmd.exe commands and you will need to drop into cmd.exe, or append the call to cmd.exe before the command. (cmd.exe /c "#the_command_here")

## System Information

```powershell
echo %DATE% %TIME%

hostname

systeminfo

systeminfo | findstr /B /C:"OS Name" /C:"OS Version"

wmic csproduct get name

wmic computersystem list brief

wmic product get name,version

echo %PATH%
```
## User Information
```powershell
whoami

net users

net localgroup administrators

net group administrators

wmic rdtoggle list

wmic group list

wmic netlogin get name,lastlogon,badpasswordcount

wmic netclient list brief

doskey /history > history.txt
```
