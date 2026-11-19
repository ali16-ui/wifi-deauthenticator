<div align="center">

<h1>AH Wifi Killer — Educational WiFi Deauthentication Toolkit</h1>

[English](#english) 

**Python • Linux • aircrack-ng • mdk4**

</div>

---

## English

### Overview

**AH Wifi Killer** is an interactive CLI toolkit for studying and testing WiFi deauthentication behavior in controlled environments. It discovers wireless interfaces, scans nearby networks, and can run deauth flows through **mdk4** or **aircrack-ng**.

> **Legal notice:** Use this software only on networks you own or have explicit written authorization to test. Unauthorized use is illegal. The author assumes no liability for misuse.

### Features

| Feature | Description |
|---|---|
| Interactive scanning | Discover nearby access points with channel and BSSID details |
| Dual attack backends | Choose **mdk4** (aggressive) or **aircrack-ng** (stable) |
| Interface detection | Automatically lists IEEE 802.11 wireless adapters |
| Monitor mode setup | Enables monitor mode on the selected interface |
| Dependency checks | Verifies root access and required system tools |
| Colored CLI | Clear terminal feedback for scan and attack status |

### Requirements

- **OS:** Linux
- **Runtime:** Python 3.x
- **Privileges:** Root (`sudo`)
- **Hardware:** Wireless adapter with monitor-mode support

#### System packages

```bash
sudo apt update
sudo apt install aircrack-ng mdk4
```

#### Python packages

Create and activate a virtual environment, then install the dependencies:

```bash
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```

Core libraries used by the tool: `scapy`, `termcolor`.

### Installation

```bash
git clone https://github.com/Hamed-Gharghi/wifi-deauther.git
cd wifi-deauther
sudo chmod +x wifi_deauther.py
```

### Usage

Launch the interactive menu:

```bash
sudo python3 wifi_deauther.py
```

Typical flow:

1. Select a wireless interface
2. Choose an attack backend (`mdk4` or `aircrack-ng`)
3. Pick a target network (or all networks)
4. Stop with `Ctrl+C`

#### Command-line options

```text
-i, --interface   Wireless interface name
-t, --target      Target WiFi BSSID (MAC address)
-g, --gateway     Gateway MAC address (optional)
-n, --count       Number of deauthentication packets (default: 1000)
```

Example:

```bash
sudo python3 wifi_deauther.py -i wlan0 -t AA:BB:CC:DD:EE:FF -n 2000
```

### Attack methods

| Method | Strengths | Best for |
|---|---|---|
| **mdk4** | Higher packet rate; can focus on clients | Aggressive lab testing |
| **aircrack-ng** | More stable; lower resource use | Broader adapter compatibility |

### Project structure

```text
wifi-deauther/
├── wifi_deauther.py   # Main CLI application
├── requirements.txt   # Python dependencies
├── LICENSE            # MIT License
└── README.md          # Documentation (EN)
```

### Disclaimer

This project is intended strictly for education, research, and authorized security testing. Running deauthentication attacks without permission may violate local laws and network policies. Always obtain consent before testing.

### License

Released under the [MIT License](LICENSE).

### Author

**Hamed Gharghi**  
GitHub: [@ali16-ui](https://github.com/ali16-ui)

If this project helps your learning or lab work, consider starring the repository.

---

