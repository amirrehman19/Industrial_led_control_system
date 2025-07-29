# 🚦 Industrial Web-Controlled LED Signal System

This project is designed to control industrial-grade red and green LED indicators using:
- ✅ Web-based relay switching via ESP32 (Ethernet)
- ✅ High-power LED driving circuit using Arduino Nano, MOSFETs, and LED drivers

The system is ideal for **industrial entrances** where visual signals (STOP/GO) are needed for traffic or worker flow control.

... (truncated in preview; full version in repo) ...

- Relays are toggled by visiting:
  `http://<esp32-ip>/relay1_on` or `/relay1_off`
- Each relay controls one of the two LED driver circuits (green or red) via Arduino Nano
- NO contact → Green ON; NC contact → Red ON

---

## 🔌 Connections (Summary)

**ESP32 to Relay Board**  
Digital Pins: `14, 27, 26, 13, 32, 33, 25, 21`  
Controls relays via web interface.

**Arduino Nano to LED Driver Circuit**  
- Uses N-channel MOSFET to control LED current
- Uses relay as hardware safety cutoff
- Powered via 5V regulator (7805) + 1N4007 protection

Check `Schematics/relay_through_web.xlsx` for full wiring.

---

## 🧠 Features

- ✅ Real-time web control over 8 independent LED circuits
- ✅ Simple Arduino Nano LED driver with MOSFET logic
- ✅ Modular: Easily scale for more relays
- ✅ Status feedback via browser

---

## 🛠 Code Overview

### 1. ESP32 Web Relay Control
📄 [`esp32_webrelay.ino`](ESP32_WebRelay_Control/esp32_webrelay.ino)

Handles Ethernet config + relay toggle via web requests

### 2. Arduino Nano LED Driver
📄 [`nano_led_driver.ino`](ArduinoNano_Code/nano_led_driver.ino)

Turns LED ON/OFF based on relay input from ESP32-controlled circuit

---

## 🔗 Web Control Examples

- Turn on green light:  
  `http://192.168.78.152/relay1_off` (connects NO, activates green)
  
- Turn on red light:  
  `http://192.168.78.152/relay1_on` (connects NC, activates red)

---

## 📷 Media

_Add photos or diagrams to `/media` for clarity._

---

## 📁 Files

- `Schematics/relay_through_web.xlsx` — All connections and wiring diagrams
- `ArduinoNano_Code/` — Nano source code
- `ESP32_WebRelay_Control/` — ESP32 Web Server code

---

## 👨‍💻 Author

Developed by **Amir** for an industrial control project.


