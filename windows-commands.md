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

<details>
<summary>Wege aus der Upgrade-Falle für Windows 11</summary>

Zusammenfassung der Schritte aus c't 5/2025, S. 60–63 ("Raus hier!", Axel Vahldiek).

## Vorab (kostenlos prüfen)

- *TPM* im BIOS aktivieren, falls es nur deaktiviert ist.
- *CSM/Legacy auf UEFI* umstellen, falls möglich. Achtung: Partitionierung und Bootloader müssen mit angepasst werden (Anleitung: c't 14/2019).

## c't-Registry-Trick

1. *Prüfen*: winver zeigt die laufende Version. Die CPU muss SSE4.2 können (Intel Core-i ab 2008, AMD ab Bulldozer 2011).
2. *Backup* anlegen, zum Beispiel mit c't-WIMage (ct.de/wimage).
3. Über **ct.de/y7vh** zwei Dateien laden: die c't-REG-Datei und das Media Creation Tool (MCT). Das MCT nicht per Google suchen, es gibt mehrere Versionen.
4. *REG-Datei* per Doppelklick importieren und die Nachfrage bestätigen. Sie setzt zwei Einträge:
   - HKLM\SYSTEM\Setup\MoSetup → AllowUpgradesWithUnsupportedTPMOrCPU (DWORD)
   - HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\HwReqChk → HwReqChkVars (Multi-SZ)
5. mediacreationtool.exe starten, die Lizenz akzeptieren und die vorausgewählte Sprache/Edition mit "Weiter" übernehmen. Dann *"ISO-Datei"* wählen und einen Speicherort mit etwa 5 GB freiem Platz angeben. Am Ende auf "Fertig stellen" klicken.
6. Die ISO im Explorer doppelklicken, sie wird als virtuelles Laufwerk eingebunden. Dort *Setup.exe* starten.
7. Mit "Weiter" startet die Update-Suche. Das Fenster verschwindet dabei eventuell hinter dem Explorer. Lizenz akzeptieren.
8. Den Hinweis "Stellen Sie sicher, dass genügend freier Speicherplatz …" ignorieren, solange sich der Kreis dreht. Benötigt werden maximal 20 GB.
9. Bei "Worum Sie sich kümmern sollten" (CPU nicht unterstützt) auf *"Aktualisieren"* klicken.
10. Bei "Bereit für die Installation" muss *"Persönliche Dateien und Apps behalten"* angehakt sein, sonst droht Datenverlust.
11. Auf "Installieren" klicken. Der PC startet mehrmals neu.
12. Bei den Datenschutzfragen jeweils die untere Antwort wählen und mit "Annehmen" bestätigen.
13. Zum Schluss mit winver prüfen, ob 24H2 läuft.

## Wichtig

- Der Trick hilft nur bei *Upgrades*, nicht bei Neuinstallationen.
- Windows aktualisiert sich danach *weiterhin nicht selbst*. Bei jedem Versionswechsel muss das Upgrade von Hand wiederholt werden.
- Microsoft könnte den Trick jederzeit per Update blockieren.
- *Stand 30.09.2026: 24H2 Home/Pro bekommt nur bis zum **13.10.2026* Updates. Der Wechsel auf 25H2 oder neuer steht an. Ob der Trick dafür noch funktioniert, sagt der Artikel nicht.
- Dauerhafte Lösung laut c't: Wechsel auf Linux oder macOS.
</details>

## Win 11 Neuinstallation
```bash
Shift + F10
```
```bash
regedit
```
```bash
HKEY_LOCAL_MACHINE\SYSTEM\Setup\LabConfig
BypassTPMCheck = 1
BypassSecureBootCheck = 1
```

oder

ISO von Microsoft - [https://www.microsoft.com/de-de/software-download/windows11](https://www.microsoft.com/de-de/software-download/windows11)
- → Rufus - [https://rufus.ie/de](https://rufus.ie/de)
- → „Remove requirement for 4GB+ RAM, Secure Boot and TPM 2.0“
- → USB booten
- → Clean Install

