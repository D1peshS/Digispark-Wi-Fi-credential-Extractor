# 🔐 Digispark Wi-Fi Credential Extractor (ATtiny85 HID Payload)

This project demonstrates how to use a **Digispark ATtiny85** USB device to emulate a keyboard (HID) and extract the **currently connected Wi-Fi SSID and password** from a Windows machine. The result is saved silently to a `.txt` file on the desktop.

---

## 🚀 What It Does

- Emulates a keyboard (HID attack vector)
- Opens PowerShell via `Win + R`
- Detects the active Wi-Fi SSID
- Extracts the password using:
  ```powershell
  netsh wlan show profile name=<SSID> key=clear
  
Writes the credentials to wifi_password.txt on the user's desktop

🧠 Why I Built This

Originally intended as a quick test project, it became a great exercise in real-world debugging, scripting, and hardware hacking:

    🐛 Solved keyboard buffer overflows and mistyped commands

    ⚡ Slowed typing down to avoid HID glitches

    🔁 Broke down long PowerShell commands to fit Digispark memory limits

    🔐 Learned the limitations of email exfiltration via PowerShell on constrained devices

    🧰 Switched to file logging for a 100% reliable payload

🔨 Tools & Tech

    Digispark ATtiny85 (USB HID emulation)

    Arduino IDE for firmware upload

    PowerShell for scripting the payload

📁 Output Example

    wifi_password.txt:

    SSID name              : "MyWifi"
    Authentication         : WPA2-Personal
    Cipher                 : CCMP
    Key Content            : BadPassword

    Windows 10/11 as the target OS
