# ⚡ IoT-Based Smart Energy Meter using ESP32

This project is a low-cost, real-time smart energy meter using the **ESP32** microcontroller, designed to monitor voltage, current, and power consumption using sensors like **ACS712** and **ZMPT101B**, with remote data monitoring and control through the **Blynk IoT platform**.

---

## 📌 Project Overview

The smart energy meter reads electrical parameters, calculates power, and transmits data to a mobile app using Wi-Fi. It also includes a relay-controlled load switch for remote ON/OFF functionality.

### Key Features:
- Real-time monitoring of Vrms, Irms, and Power
- LCD display output
- Remote monitoring via **Blynk mobile app**
- Wi-Fi connectivity with ESP32
- Load control (bulb/relay) through Blynk interface

---

## 🧠 System Components

### 🔧 Hardware:
| Component              | Description                              |
|------------------------|------------------------------------------|
| ESP32                  | Wi-Fi-enabled microcontroller            |
| ACS712                 | Hall-effect current sensor               |
| ZMPT101B               | High-precision AC voltage sensor         |
| LCD 16x2 with I2C      | For local display of voltage and current |
| Relay Module           | Load control (bulb or appliance)         |
| Bulb/Load              | Connected load for testing               |
| Jumper Wires, Breadboard | For prototyping                       |

### 💻 Software:
- **Arduino IDE** (ESP32 board package installed)
- **Blynk App** (use Blynk legacy or new Blynk IoT platform)
- Blynk Library (`BlynkSimpleEsp32.h`)

---

## 🔌 Circuit Overview

**Sensor → ESP32 → LCD + Wi-Fi → Blynk App**

- ACS712 connected to analog pin (e.g., GPIO 34)
- ZMPT101B connected to analog pin (e.g., GPIO 35)
- Relay module connected to digital pin (e.g., GPIO 25)
- I2C LCD to ESP32 via SDA/SCL
- ESP32 connects to Wi-Fi and pushes data to the Blynk dashboard

---

## 📲 Mobile Dashboard Setup (Blynk)

1. Create a new project
2. Add the following widgets:
   - **Gauge** for Voltage → V1
   - **Gauge** for Current → V2
   - **Gauge or Value Display** for Power → V3
   - **Button** (for Relay) → V4
3. Copy your **Auth Token** into the code

---

## 🔧 Calibration Note

To convert analog values to voltage and current accurately:
- Adjust `voltageFactor` (for ZMPT101B)
- Adjust `currentFactor` (for ACS712)
- Use known loads to fine-tune values

---

## 🧪 Testing

- ✅ Real-time values displayed on LCD
- ✅ Power = Vrms × Irms calculation accurate
- ✅ Control load via app switch
- ✅ ESP32 stable under Wi-Fi connection

---

## 📁 Files Included

- `smart_energy_meter.m` → Arduino code in `.m` format (rename to `.ino` for uploading)
- `README.md` → This file

---

## 🧑‍💻 Developed By

- **Mohamed Fawzan N** – RA2211004010643  
- **Sudharshan V** – RA2211004010645  
- **Rajendra G** – RA2211004010647
-  **Jamison B** – RA2211004010646

---

## 📚 References

1. ACS712 Datasheet  
2. ZMPT101B Datasheet  
3. Blynk Docs: https://docs.blynk.io  
4. ESP32 Arduino Core: https://github.com/espressif/arduino-esp32

---

## 📎 License

This project is licensed for academic and learning purposes. Commercial usage requires permission from the authors.
