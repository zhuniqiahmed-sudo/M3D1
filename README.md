# M3D1
use this tool  for testing only



    # M3D1'S TOOLS

A terminal-based network diagnostic and automation suite written in Python, featuring automatic IP rotation via the Tor network.

---

## 💻 Installation Guide

Choose the instructions below that match your operating system. Ensure you have **Python 3.8+** installed before proceeding.

### 🐧 1. Linux (Ubuntu / Debian / Kali)
Open your terminal and run the following commands to install Tor, configure dependencies, and start the application:

```bash
# Clone the repository
git clone https://github.com
cd m3d1-tools

# Update packages and install Tor
sudo apt update && sudo apt install -y tor python3-pip python3-venv

# Enable Tor control port configuration
echo "ControlPort 9051" | sudo tee -a /etc/tor/torrc
echo "CookieAuthentication 1" | sudo tee -a /etc/tor/torrc
sudo systemctl restart tor

# Set up virtual environment and run
python3 -m venv venv
source venv/bin/activate
pip install stem requests
python3 rotator.py
```

---

### 🏹 2. Arch Linux
Arch users can set up the tool using `pacman` and `systemctl`:

```bash
# Clone the repository
git clone https://github.com
cd m3d1-tools

# Install Tor
sudo pacman -Syu tor python-pip

# Configure Tor Control Port
sudo echo -e "ControlPort 9051\nCookieAuthentication 1" >> /etc/tor/torrc
sudo systemctl enable --now tor

# Set up Python environment and run
python3 -m venv venv
source venv/bin/activate
pip install stem requests
python3 rotator.py
```

---

### 🍏 3. macOS
On macOS, managing the Tor daemon is easiest using **Homebrew**:

```bash
# Clone the repository
git clone https://github.com
cd m3d1-tools

# Install Tor via Homebrew
brew install tor

# Configure Tor (Ensure paths match your system layout)
echo -e "ControlPort 9051\nCookieAuthentication 1" >> /opt/homebrew/etc/tor/torrc
brew services restart tor

# Set up Python environment and run
python3 -m venv venv
source venv/bin/activate
pip install stem requests
python3 rotator.py
```

---

### 🪟 4. Windows
Windows requires running the Tor expert bundle manually in the background:

1. **Download Tor:** Download the *Tor Expert Bundle* from the official Tor Project website and extract it.
2. **Configure Tor:** Create a file named `torrc` inside your extracted Tor folder and add:
   ```text
   ControlPort 9051
   CookieAuthentication 1
   ```
3. **Start Tor:** Open PowerShell as Administrator, navigate to your Tor folder, and run:
   ```powershell
   .\tor.exe -f .\torrc
   ```
4. **Run the Script:** Open a second PowerShell window and run:
   ```powershell
   git clone https://github.com
   cd m3d1-tools
   python -m venv venv
   .\venv\Scripts\Activate.ps1
   pip install stem requests
   python rotator.py
   ```

---

## ⚙️ Configuration Notes
* **Tor Verification:** If the tool fails to rotate, verify your firewall allows internal communication on port `9051` (Control Port) and port `9050` or `9150` (SOCKS Proxy).
* **Exit:** Press `Ctrl + C` in your terminal interface to stop rotation routines and exit gracefully.

