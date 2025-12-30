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