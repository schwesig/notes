```bash
winget.exe upgrade --all -h --include-unknown --accept-package-agreements --accept-source-agreements --silent
```

```bash
C:\Windows\System32\shutdown.exe -s -t 0
```

## Systembereinigung
```bash
sfc /scannow
```
```bash
DISM.exe /Online /Cleanup-Image /StartComponentCleanup
```

```bash
DISM.exe /Online /Cleanup-Image /RestoreHealth
```

## Temporaere Dateien Loeschen
```bash
cleanmgr /sageset:1
```
```bash
cleanmgr /sagerun:1
```
### manuell
```bash
net stop wuauserv
net stop bits
net stop cryptsvc
```

```bash
ren C:\Windows\SoftwareDistribution SoftwareDistribution.old
ren C:\Windows\System32\catroot2 catroot2.old
```

```bash
C:\$WINDOWS.~BT
C:\$WINDOWS.~WS
```

```bash
DE
takeown /F C:\$WINDOWS.~BT /R /D J
takeown /F C:\$WINDOWS.~WS /R /D J

EN
takeown /F C:\$WINDOWS.~BT /R /D Y
takeown /F C:\$WINDOWS.~WS /R /D Y

rmdir /S /Q C:\$WINDOWS.~BT
rmdir /S /Q C:\$WINDOWS.~WS
```

```bash
net start cryptsvc
net start bits
net start wuauserv
```

## Win Install w/o Online
Shift+F10
```bash
oobe\bypassnro
```

or
```bash
reg add HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\OOBE /v BypassNRO /t REG_DWORD /d 1 /f
shutdown /r /t 0
```

or
```bash
start ms-cxh:localonly
```

## Manuelle schrittweise Win10/11 Updates
- https://www.google.com/search?q=Win10_20H2_English_x64.iso&rlz=1C1GCEA_enDE1131DE1132&sourceid=chrome&ie=UTF-8
- https://github.com/awesome-windows11/windows11
- https://github.com/awesome-windows11/windows11/tree/main/iso
- https://github.com/AveYo/MediaCreationTool.bat
- https://uupdump.net/download.php?id=bdfc98d8-d2f5-4b1c-b75c-bb37c15ccbb6&pack=de-de&edition=core%3Bprofessional

## Activate
- https://github.com/massgravel/microsoft-activation-scripts
1. Click the Start Menu, type PowerShell, and open it.
2. Copy and paste the code below and press Enter.

For Windows 8.1, 10 and 11:
```bash
irm https://get.activated.win | iex
```
If the above is blocked (by ISP/DNS), try this (needs updated Windows 10 or 11):
```bash
iex (curl.exe -s --doh-url https://1.1.1.1/dns-query https://get.activated.win | Out-String)
```

3. In the menu that appears, type the number corresponding to one of the Green options.

## Windows Update Falle
- https://www.heise.de/select/ct/2025/5/2502011510659511876
- https://www.heise.de/select/ct/2025/5/2500716443278609757
- https://www.heise.de/select/ct/2025/5/softlinks/y7vh?wt_mc=pred.red.ct.ct052025.060.softlink.softlink
  - ct.de/y7vh
