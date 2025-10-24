`winget.exe upgrade --all -h --include-unknown --accept-package-agreements --accept-source-agreements --silent`

`C:\Windows\System32\shutdown.exe -s -t 0`

## Systembereinigung
```bash
sfc /scannow
```
```bash
DISM.exe /Online /Cleanup-Image /RestoreHealth
```

## Win Install w/o Online
Shift+F10
```bash
oobe\bypassnro
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
C:\$WINDOWS.~BT
```
```bash
C:\$WINDOWS.~WS
```