# Windows_Triage

# System Information

echo %DATE% %TIME%
hostname
systeminfo
systeminfo | findstr /B /C:"OS Name" /C:"OS Version"
wmic csproduct get name
wmic computersystem list brief
wmic product get name,version
echo %PATH%
