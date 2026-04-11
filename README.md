# SYS_MONITOR v2.0

> A real-time terminal system monitor built with Python and curses.  
> Watch CPU, memory, disk, network, and processes — live, in your command line.

![Python](https://img.shields.io/badge/Python-3.7+-yellow?style=flat-square&logo=python)
![Platform](https://img.shields.io/badge/Platform-Windows%20%7C%20Linux%20%7C%20macOS-yellow?style=flat-square)
![License](https://img.shields.io/badge/License-MIT-yellow?style=flat-square)

---

## Features

- **CPU** — Overall usage, per-core bars, clock frequency, 60-second sparkline
- **Memory** — RAM and swap in GB, load average, sparkline history
- **Disk** — Per-mount usage bars for every drive (C:, D:, /, /home)
- **Network** — Per-interface stats, live speeds, IP, packet counts (TAB to switch)
- **Processes** — Top 20 by CPU; arrow keys to select, K to kill with confirmation
- **System Log** — Live timestamped event stream, color-coded by severity

---

## Requirements

- Python 3.7+
- `psutil` library
- Windows only: `windows-curses` (built-in on Linux/macOS)

---

## Installation & Usage

### Windows

```bash
pip install psutil windows-curses
python sysmon.py
```

Or download **sysmon.exe** from [Releases](https://github.com/kailash1234-visual/Terminal-Monitor-System/releases/latest) — no Python required.

### Linux / macOS

```bash
pip install psutil
python3 sysmon.py
```

### Build EXE (Windows)

```bash
pip install pyinstaller
pyinstaller --onefile --console sysmon.py
# Output: dist\sysmon.exe
```

> Run `dist\sysmon.exe` from Command Prompt — not by double-clicking.

---

## Keyboard Controls

| Key | Action | Panel |
|-----|--------|-------|
| `↑` `↓` | Select a process | Processes |
| `K` | Kill selected process (Y/N confirmation) | Processes |
| `TAB` | Cycle network interfaces (WiFi → ETH → Loop) | Network |
| `R` | Force immediate data refresh | Global |
| `Q` | Quit the application | Global |
| `Ctrl+C` | Force quit | Global |

---

## Panel Reference

<details>
<summary><b>CPU</b></summary>

- Overall CPU % with NOMINAL / WARN / CRIT badge
- Per-core bars — one row per logical core
- Current clock frequency in GHz
- 60-second sparkline history
- Badge turns amber above 65%, red above 85%

</details>

<details>
<summary><b>Memory</b></summary>

- RAM used vs total displayed in GB
- RAM and swap usage bars
- System load average on Linux/macOS
- 60-second sparkline history
- High swap = memory pressure warning

</details>

<details>
<summary><b>Disk</b></summary>

- Usage bar for every mounted partition
- Shows mount point, used %, used GB, total GB
- Total bytes read and written since boot
- Color shifts amber at 65%, red at 85%

</details>

<details>
<summary><b>Network</b></summary>

- Press TAB to cycle between interfaces
- Interface name, type (WiFi / ETH / Loop), and IP
- Live upload and download speed
- Total bytes sent and received
- 60-second download sparkline

</details>

<details>
<summary><b>Processes</b></summary>

- Top 20 processes sorted by CPU usage
- Columns: Name, PID, CPU%, MEM%, Status
- Use ↑/↓ to highlight a row
- Press K — popup asks Y to confirm or N to cancel
- System processes may be protected (Access Denied logged)

</details>

<details>
<summary><b>System Log</b></summary>

- Live timestamped event stream
- Green = info, amber = warning, red = error
- Auto-logs CPU or RAM alerts above 90%
- Logs process kills, errors, and startup info
- Keeps last 200 log lines in memory

</details>

---

## Website

The project includes a live website with two pages:

- **Landing page** — project info, install guide, download button
- **Monitor demo** — browser-based live dashboard

🌐 [Visit Website]

https://terminal-system-monitor.onrender.com

---

👤 Author

Selva Kailash S —  @kailash1234-visual
