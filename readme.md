# 🔌 ESP32-C3 SuperMini 8-Channel Relay Board  
Smart IoT Home Automation with **Blynk, Arduino IoT Cloud, Tasmota, Firebase, Alexa, Google Home & Home Assistant**  

![PCB 3D](docs/3D_PCB.png)  
*3D Render of ESP32-C3 8CH Relay Board*  

---

## 📌 Overview  
This project is an **8-channel relay controller** based on the **ESP32-C3 SuperMini**.  
It provides **multi-platform IoT support** out of the box for:  

- 🌐 **Blynk IoT Cloud**  
- 🛰️ **Arduino IoT Cloud**  
- 🖥️ **Home Assistant (via MQTT)**  
- 🗣️ **Amazon Alexa voice control**  
- 🎤 **Google Home voice control**  
- 🏠 **Tasmota Firmware** (for power users)  
- 🔥 **Google Firebase integration**  

✨ Features:  
- ✅ 8 relays (up to 250VAC / 10A each)  
- ✅ Works with **Wi-Fi, Cloud, Voice Assistants**  
- ✅ Physical switches with **independent sync** (hotel-light style)  
- ✅ EEPROM save (state remembered after reboot)  
- ✅ Multi-firmware support (Arduino, Tasmota, etc.)  
- ✅ Compact PCB design with onboard PSU  

---

## 🖥️ Hardware  

### 🔹 Schematic  
![Schematic](docs/Schematic.png)  

### 🔹 PCB Layout  
![PCB](docs/PCB.png)  

### 🔹 3D View  
![3D PCB](docs/3D_PCB.png)  

---

## 📦 Bill of Materials (BOM)  
Main components (see `BOM.xlsx` for full list):  

| Component | Part | Qty |
|-----------|------|-----|
| MCU       | ESP32-C3 SuperMini | 1 |
| Relay     | G5NB-1A-E-DC5V (5V, 10A) | 8 |
| Driver    | ULN2803 | 1 |
| Power     | HLK-PM01 (AC-DC 230V → 5V) | 1 |
| DC Reg    | LM2596 Buck Converter | 1 |
| LEDs + Resistors | Status indicators | 8 |
| Misc.     | Diodes, Caps, Connectors | Various |

---

## ⚡ Pin Mapping (ESP32-C3 → Relays)  

| Relay | ESP32-C3 GPIO |
|-------|--------------|
| RLY1  | D0 |
| RLY2  | D1 |
| RLY3  | D2 |
| RLY4  | D3 |
| RLY5  | D4 |
| RLY6  | D5 |
| RLY7  | D6 |
| RLY8  | D7 |

(Adjust firmware if using different pins.)  

---

## 🔧 Firmware Options  

You can flash **any firmware** depending on your ecosystem:  

### 1️⃣ Blynk IoT  
- Supports mobile + web dashboard  
- Auto reconnect & sync  
- EEPROM save  

👉 Example sketch: [`firmware/blynk_esp32c3_8ch.ino`](firmware/blynk_esp32c3_8ch.ino)  

---

### 2️⃣ Arduino IoT Cloud  
- Works with **Arduino Cloud dashboards**  
- Control relays from app & web  
- OTA firmware updates  

👉 Example sketch: [`firmware/arduino_iot_esp32c3_8ch.ino`](firmware/arduino_iot_esp32c3_8ch.ino)  

---

### 3️⃣ Tasmota Firmware  
- Flash Tasmota & use MQTT/Home Assistant  
- Auto-discovery in Home Assistant  
- Web dashboard built-in  

👉 Use template in Tasmota:  
```
{"NAME":"ESP32C3-8CH","GPIO":[0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0],"FLAG":0,"BASE":18}
```
(Edit GPIO mapping for relays D0–D7)  

---

### 4️⃣ Google Firebase  
- Store relay states in cloud  
- Sync between multiple devices  

👉 Example: [`firmware/firebase_esp32c3_8ch.ino`](firmware/firebase_esp32c3_8ch.ino)  

---

### 5️⃣ Alexa + Google Home  
- Works via **Sinric Pro** or **ESP Alexa library**  
- Voice control of each relay: *“Alexa, turn on Relay 1”*  

👉 Example: [`firmware/alexa_googlehome_esp32c3_8ch.ino`](firmware/alexa_googlehome_esp32c3_8ch.ino)  

---

### 6️⃣ Home Assistant  
- Connect via MQTT  
- Supports **two-way sync**  
- YAML auto-discovery  

👉 Example config in `configuration.yaml`:  
```yaml
switch:
  - platform: mqtt
    name: "Relay 1"
    state_topic: "esp32c3/relay1/state"
    command_topic: "esp32c3/relay1/set"
    payload_on: "ON"
    payload_off: "OFF"
    retain: true
```

---

## 🚀 How to Flash  
1. Connect ESP32-C3 SuperMini via USB  
2. Select **ESP32-C3 Dev Module** in Arduino IDE  
3. Upload chosen firmware  
4. Open Serial Monitor @ 115200 baud  
5. Control relays from **Blynk / Arduino Cloud / Alexa / Google Home / Home Assistant** 🎉  

---

## 🌍 Applications  
- Smart home automation  
- Appliance control  
- IoT-based remote switching  
- Voice-enabled devices  
- Industrial automation  

---

## 🛠️ Future Roadmap  
- Energy monitoring add-on  
- OTA updates across all firmware versions  
- Matter protocol support (for full Google/Alexa native integration)  

---

## 📧 Author  
👨‍💻 Designed by **ElectroIoT**  
📩 [electroiot.in@gmail.com](mailto:electroiot.in@gmail.com)  
🌐 [https://ElectroIoT.in](https://ElectroIoT.in)  

---

⚡ Open-source hardware + firmware for makers & DIY enthusiasts  
