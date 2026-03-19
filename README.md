# 🌿 Greenhouse Automation System

This project represents an automated monitoring and control system for a greenhouse, built using **Arduino** technology. The system's goal is to optimize plant growth conditions by automatically regulating temperature, humidity, and ventilation, thereby reducing costs and human intervention.

---

## 🛠️ Components Used (Hardware)

To build this system, the following components were used:
* **Microcontroller:** Arduino Nano (the central processing unit)
* **Temp & Humidity Sensor:** DHT11
* **Light Sensor:** Photoresistor module (for Day/Night detection)
* **Door Actuator:** SG90 Servo motor
* **Ventilation:** AFB0405MA-A Fan (controlled via 2N2222 transistor and 1kΩ resistor)
* **Others:** Breadboard, Jumper wires, resistors.



---

## ⚙️ Operational Logic

The system makes real-time decisions based on sensor data, following a specific set of logic rules:

| Condition | Door Action (Servo) | Fan Action |
| :--- | :--- | :--- |
| **Temp > 25°C (Day)** | Open 🔓 | Off ⚪ |
| **Humidity > 50% (Day)** | Closed 🔒 | On 🟢 |
| **Temp > 30°C & Humidity > 50%** | Open 🔓 | On 🟢 |
| **High Temp or Humidity (Night)** | Closed 🔒 | On 🟢 |

*The system distinguishes between day and night using the photoresistor, adapting ventilation to protect plants during the night.*

---

## 🔌 Connections (Circuit Diagram)

The components are connected to the Arduino Nano as follows:
* **DHT11:** Digital Pin 8
* **Light Sensor:** Digital Pin 9
* **Fan (via Transistor):** Digital Pin 7
* **Servo Motor:** PWM Pin 6



---

## 🚀 How to Use

1. **Hardware:** Assemble the connections according to the circuit diagram (see the section above).
2. **Software:** Upload the Arduino code (provided in the `/src` folder) using the Arduino IDE.
3. **Monitoring:** The system will automatically begin reading data and controlling the actuators (servo and fan).

---

## 📈 Benefits
* **Efficiency:** Reduced energy consumption by activating components only when necessary.
* **Productivity:** Maintains an ideal microclimate for plants 24/7.
* **Accessibility:** Low-cost solution based on widely available components.

---
*Project developed as part of a hardware automation systems study.*
