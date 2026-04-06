Terminal System Monitor
A lightweight, real-time CLI dashboard for monitoring system resources (CPU, Memory, Disk, and Network).

🚀 Features
Real-time CPU Usage: Track load across all cores.

Memory Tracking: Monitor RAM and Swap usage.

Disk I/O: View read/write speeds and storage capacity.

Network Stats: Monitor data sent and received.

Standalone Executable: Build into a single .exe for easy distribution.

🛠 Installation
Clone the repository:

Bash
git clone https://github.com/yourusername/terminal-sysmon.git
cd terminal-sysmon
Install dependencies:
(Ensure you have Python 3.x installed)

Bash
pip install psutil
💻 Usage
To run the script directly:

Bash
python sysmon.py
📦 Building the Executable
To bundle the application into a single, portable executable file using PyInstaller, run:

Bash
pyinstaller --onefile --console sysmon.py
After the process finishes, you will find the standalone file in the dist/ folder.

📋 Requirements
Python 3.7+

psutil: For retrieving system information.

PyInstaller: (Optional) Only needed if you want to build the .exe.
