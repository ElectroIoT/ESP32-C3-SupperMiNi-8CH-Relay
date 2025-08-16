# 🔌 ESP32-C3 8-Channel Smart Relay Board for Home Automation

Welcome to the official repository for the **ESP32-C3-based 8-Channel Wi-Fi Relay Controller Board**. This board is designed to automate lights, fans, appliances, and more using your local Wi-Fi network and smart assistants.

![3D PCB View](images/3d_pcb.png)
> 🚀 Compact | 🔧 DIY Friendly | 🧠 Smart | 🏠 Home Assistant Ready

---

## 📦 Features

- ✅ **ESP32-C3 SuperMini** — Wi-Fi + BLE support
- ✅ **8 Relays (10A/250V)** — Control high-voltage devices
- ✅ **ULN2803A** — Integrated relay driver IC
- ✅ **HLK-PM01 AC-DC Module** — Safe onboard AC to 5V conversion
- ✅ **LM2596 Buck Converter** — 5V to 3.3V for ESP32
- ✅ **I2C Header** — OLED, DHT11, BMP280, etc.
- ✅ **Extra GPIOs** — For buttons, LEDs, or more sensors
- ✅ **Works with ESPHome, Tasmota, Arduino**

---

## 🧠 How It Works

1. ESP32-C3 receives commands via Wi-Fi.
2. GPIOs control each relay through ULN2803A.
3. Relays switch AC appliances (lights, fans, etc.).
4. I2C and extra GPIOs allow you to expand with sensors and displays.

---

## 🖼️ Gallery

| 3D View | PCB Top | Schematic |
|--------|----------|------------|
| ![3D](images/3d_pcb.png) | ![Top](images/pcb_top.png) | ![Schematic](images/schematic.png) |

---

## 🔌 Pin Mapping

| Relay | GPIO |
|-------|------|
| Relay 1 | GPIO0 |
| Relay 2 | GPIO1 |
| Relay 3 | GPIO2 |
| Relay 4 | GPIO3 |
| Relay 5 | GPIO4 |
| Relay 6 | GPIO5 |
| Relay 7 | GPIO6 |
| Relay 8 | GPIO7 |

---

## ⚙️ Firmware Options

### 🏠 ESPHome (Recommended for Home Assistant)
```yaml
esphome:
  name: smart-relay-board

esp32:
  board: esp32-c3-dev

wifi:
  ssid: "YourWiFi"
  password: "YourPassword"

switch:
  - platform: gpio
    pin: GPIO0
    name: "Relay 1"
  - platform: gpio
    pin: GPIO1
    name: "Relay 2"
  # Add remaining relays as needed
```

### 🌐 Tasmota Template
```text
{"NAME":"ESP32-8Relay","GPIO":[0,1,2,3,4,5,6,7],"FLAG":0,"BASE":1}
```

### 💻 Arduino Example
```cpp
void setup() {
  for (int pin = 0; pin < 8; pin++) {
    pinMode(pin, OUTPUT);
    digitalWrite(pin, LOW); // Relays OFF
  }
}

void loop() {
  digitalWrite(0, HIGH); // Turn ON Relay 1
  delay(1000);
  digitalWrite(0, LOW);  // Turn OFF Relay 1
  delay(1000);
}
```

---

## 📁 Repository Contents

```
ESP32C3-8Relay-Board/
├── images/
│   ├── 3d_pcb.png
│   ├── pcb_top.png
│   └── schematic.png
├── firmware/
│   ├── esphome.yaml
│   └── arduino_sketch.ino
├── gerber/
│   └── gerber_files.zip
├── schematic/
│   └── ESP32C3-RelayBoard.sch
├── bom/
│   └── BOM.csv
└── README.md
```

---

## 🔨 Hardware Required

| Component | Quantity |
|-----------|----------|
| ESP32-C3 SuperMini | 1 |
| G5NB-1A-E DC5V Relay | 8 |
| ULN2803A | 1 |
| HLK-PM01 | 1 |
| LM2596 Buck Converter | 1 |
| Screw Terminals | 8 |
| 1N4007 Diode (optional) | 8 |
| LEDs + Resistors | 8 sets |
| Push Button | 1 |
| Custom PCB | 1 |

---

## 🛒 Buy PCB

🔗 Order the PCB from [PCBWay Project Page](https://www.pcbway.com/project/shareproject/_ESP32_C3_Based_8_Channel_Smart_Home_Automation_Relay_Board_10a2824f.html)

---

## 💡 Use Cases

- Smart light/fan control via mobile or voice
- Automation with Home Assistant or Node-RED
- Remote reboot for networking equipment
- Scheduled appliance control

---

## 🙌 Credits

**Designed & Developed by:** [Manoranjan Das](https://electroiot.in)  
📬 Email: electroiot.in@gmail.com  
🔗 Website: https://electroiot.in

---

## 📜 License

This project is licensed under the **MIT License**.  
Feel free to use, modify, and share!

---

⭐ **If you like this project, please give it a star!**  
💬 *Issues, improvements, or contributions are welcome!*
# ESP32-C3-SupperMiNi-8CH-Relay
