# S1_Remo_Shell_Windows_Triage

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
