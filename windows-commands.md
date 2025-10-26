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
C:\$WINDOWS.~BT
```
```bash
C:\$WINDOWS.~WS
```

## Win Install w/o Online
Shift+F10
```bash
oobe\bypassnro
```