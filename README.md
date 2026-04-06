<div align="center">

# 🖥️ SYS_MONITOR

**A real-time terminal system monitor built with Python**

[![Python](https://img.shields.io/badge/Python-3.7%2B-blue?style=flat-square&logo=python)](https://www.python.org/)
[![Platform](https://img.shields.io/badge/Platform-Windows%20%7C%20Linux%20%7C%20macOS-lightgrey?style=flat-square)]()
[![License](https://img.shields.io/badge/License-MIT-green?style=flat-square)]()
[![Version](https://img.shields.io/badge/Version-2.0-orange?style=flat-square)]()

Monitor your CPU, memory, disk, network, and processes — all inside your terminal, live.

</div>

---

## ✨ Features

- **CPU panel** — overall usage, per-core bars, frequency, and 60s sparkline history
- **Memory panel** — RAM & swap usage with GB breakdown and load average
- **Disk panel** — per-mount usage bars and total read/write counters
- **Network panel** — per-interface stats (WiFi, Ethernet, Loopback) with live speed and packet counts. Press `TAB` to cycle interfaces
- **Process panel** — top 20 processes by CPU, with live scroll and **process killer**
- **System log** — live event log with auto-warnings for high CPU/RAM
- **Color-coded alerts** — green → amber → red as values climb
- **Adaptive layout** — resizes automatically when you resize the terminal
- **Standalone EXE** — build a single `.exe` for Windows with no Python required

---

## 📦 Installation

### Clone the repo

```bash
git clone https://github.com/your-username/sys-monitor.git
cd sys-monitor
```

### Install dependencies

**Windows:**
```cmd
pip install psutil windows-curses
```

**Linux / macOS:**
```bash
pip install psutil
```

---

## 🚀 Usage

**Windows:**
```cmd
python sysmon.py
```

**Linux / macOS:**
```bash
python3 sysmon.py
```

> Best viewed at terminal width **120+ columns** for the full layout.

---

## ⌨️ Controls

| Key | Action |
|-----|--------|
| `↑` / `↓` | Select a process |
| `K` | Kill selected process *(confirmation required)* |
| `TAB` | Cycle network interfaces |
| `R` | Force refresh |
| `Q` or `Ctrl+C` | Quit |

---

## 🏗️ Build as EXE (Windows)

Distribute a single executable — no Python needed on the target machine.

```cmd
pip install pyinstaller
pyinstaller --onefile --console sysmon.py
```

Output: `dist\sysmon.exe`

> Run the `.exe` from a **Command Prompt or terminal window** — not by double-clicking, as it needs a terminal to render the TUI.

---

## 📁 Project Structure

```
sys-monitor/
├── sysmon.py        # Main application
├── README.md        # This file
└── dist/
    └── sysmon.exe   # Built executable (after running PyInstaller)
```

---

## 🖥️ Panel Reference

<details>
<summary><strong>CPU</strong></summary>

- Overall CPU % with NOMINAL / WARN / CRIT badge
- Per-core usage bars
- Current clock frequency (GHz)
- 60-second sparkline history

</details>

<details>
<summary><strong>Memory</strong></summary>

- RAM used vs total in GB
- RAM and swap usage bars
- System load average (Linux/macOS)
- 60-second sparkline history

</details>

<details>
<summary><strong>Disk</strong></summary>

- Per-mount usage bars (C:, D:, /, /home, etc.)
- Total bytes read and written since boot

</details>

<details>
<summary><strong>Network</strong></summary>

- Cycle interfaces with `TAB` (WiFi / Ethernet / Loopback)
- Interface name, type tag, and IP address
- Live upload and download speed
- Bytes sent/received totals
- Packet TX / RX counts
- All-interfaces combined summary
- 60-second download sparkline

</details>

<details>
<summary><strong>Processes</strong></summary>

- Top 20 processes sorted by CPU
- Columns: Name, PID, CPU%, MEM%, Status
- Use `↑` / `↓` to highlight a process
- Press `K` to kill (Y/N confirmation popup)
- Color: green → amber → red by CPU load

</details>

<details>
<summary><strong>System Log</strong></summary>

- Live timestamped event log
- Auto-warns when CPU or RAM exceeds 90%
- Logs kill events, errors, and startup info
- Color-coded: 🟢 info  🟡 warn  🔴 error

</details>

---

## 🎨 Color Legend

| Color | Meaning |
|-------|---------|
| 🟢 Green | Normal (0–64%) |
| 🟡 Amber | Warning (65–84%) |
| 🔴 Red | Critical (85%+) |

---

## 🔧 Requirements

| Package | Purpose | Install |
|---------|---------|---------|
| `psutil` | System metrics | `pip install psutil` |
| `windows-curses` | Terminal UI on Windows | `pip install windows-curses` |
| `curses` | Terminal UI on Linux/macOS | Built-in |
| `pyinstaller` | Build `.exe` *(optional)* | `pip install pyinstaller` |

---

## 📋 Version History

| Version | What's new |
|---------|-----------|
| **v2.0** | Process killer (`K`), per-interface network panel (`TAB`), kill confirmation dialog, process scroll & select |
| **v1.0** | Initial release — CPU, RAM, disk, network overview, process list, system log |

---

## 🤝 Contributing

Pull requests are welcome! If you find a bug or have a feature idea, open an issue first to discuss it.

1. Fork the repo
2. Create your branch: `git checkout -b feature/my-feature`
3. Commit your changes: `git commit -m 'Add my feature'`
4. Push to the branch: `git push origin feature/my-feature`
5. Open a pull request

---

## 📄 License

This project is licensed under the MIT License — see the [LICENSE](LICENSE) file for details.

---

<div align="center">
Built with Python 🐍 · psutil · curses
</div>
