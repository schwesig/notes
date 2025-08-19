https://openbenchmarking.org/suite/pts/workstation
https://github.com/phoronix-test-suite/phoronix-test-suite

# 🔧 Linux Benchmark Guide mit Phoronix Test Suite

Dieses Dokument beschreibt, wie du CPU, RAM, Disk und GPU Benchmarks mit
der **Phoronix Test Suite (PTS)** ausführst und Ergebnisse über die Zeit
vergleichst.

------------------------------------------------------------------------

## 📦 Installation

### Ubuntu / Debian

``` bash
sudo apt update
sudo apt install phoronix-test-suite
```

### Fedora

``` bash
sudo dnf install phoronix-test-suite
```

### Arch

``` bash
sudo pacman -S phoronix-test-suite
```

------------------------------------------------------------------------

## 🚀 Komplett-Benchmark starten

Führe CPU-, RAM-, Disk- und GPU-Tests nacheinander aus:

``` bash
phoronix-test-suite batch-benchmark pts/compress-7zip pts/ramspeed pts/fio pts/glmark2
```

-   **pts/compress-7zip** → CPU\
-   **pts/ramspeed** → RAM\
-   **pts/fio** → Disk I/O\
-   **pts/glmark2** → GPU / OpenGL

Am Ende wirst du nach einem **Result-Name** gefragt.\
Beispiel: `baseline-aug2025`

------------------------------------------------------------------------

## 📊 Ergebnisse speichern & vergleichen

### Alle Runs auflisten

``` bash
phoronix-test-suite list-results
```

### Zwei Runs vergleichen

``` bash
phoronix-test-suite compare-results baseline-aug2025 kernel-6.11-test
```

➡️ Ergebnis: Tabelle mit Messwerten und %-Unterschieden.

------------------------------------------------------------------------

## 📤 Ergebnisse exportieren

-   **Als Text**

    ``` bash
    phoronix-test-suite result-file-to-text baseline-aug2025
    ```

-   **Als HTML**

    ``` bash
    phoronix-test-suite result-file-to-html baseline-aug2025
    ```

------------------------------------------------------------------------

## 🛠 Automatisierter Benchmark (mit Datum im Namen)

Folgendes Skript führt die Benchmarks aus, speichert das Ergebnis mit
dem aktuellen Datum und vergleicht es direkt mit dem letzten Lauf:

``` bash
#!/bin/bash
NAME="bench-$(date +%Y%m%d-%H%M)"
phoronix-test-suite batch-benchmark pts/compress-7zip pts/ramspeed pts/fio pts/glmark2 -R $NAME
LAST=$(phoronix-test-suite list-results | tail -2 | head -1)
echo "Vergleiche $LAST mit $NAME"
phoronix-test-suite compare-results $LAST $NAME
```

------------------------------------------------------------------------

✅ Mit diesem Setup kannst du nach Kernel-, Treiber- oder
Hardware-Änderungen systematisch vergleichen.
