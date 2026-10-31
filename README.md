# 🛡️ Smart Wearable Safety Band for Women

### An IoT-Based Emergency Alert and Real-Time GPS Location Sharing System
<p align="center">
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Platform-ESP32-blue?style=for-the-badge&logo=espressif" alt="ESP32">
  <img src="https://img.shields.io/badge/IDE-Arduino-00979D?style=for-the-badge&logo=arduino" alt="Arduino">
  <img src="https://img.shields.io/badge/Technology-IoT-orange?style=for-the-badge" alt="IoT">
  <img src="https://img.shields.io/badge/Communication-WiFi-green?style=for-the-badge" alt="WiFi">
  <img src="https://img.shields.io/badge/Status-Completed-success?style=for-the-badge" alt="Completed">
</p>

---

## 📌 Project Overview

The **Smart Wearable Safety Band for Women** is an IoT-based personal safety device designed to provide quick emergency assistance through real-time GPS location sharing.

In emergency situations, accessing a smartphone, unlocking it, and manually sharing a location can be time-consuming. To overcome this limitation, this project introduces a compact wearable safety band equipped with a dedicated emergency push button.

When the user presses the SOS button, the ESP32 processes the input, retrieves GPS coordinates from the NEO-6M GPS module, and sends the location to a designated guardian through a Telegram bot.

The system provides a simple and accessible approach to emergency communication using embedded systems and IoT technology.

---

## 🎯 Problem Statement

Women may encounter unsafe situations while travelling alone, particularly at night or in unfamiliar locations.

During emergencies, quickly communicating their current location to guardians or trusted contacts can be difficult.

Traditional mobile-based safety applications require multiple manual operations, which may delay emergency communication.

Therefore, a simple, wearable, and low-cost emergency alert system is needed to enable faster location sharing with minimal user interaction.

## 💡 Proposed Solution

We developed a Smart Wearable Safety Band that enables emergency location sharing through a single button press.

The device integrates an ESP32 microcontroller, GPS module, and Telegram Bot API to provide an emergency alert mechanism.

**Working concept:**

Emergency Button Press → GPS Location Retrieval → ESP32 Processing → Wi-Fi Communication → Telegram Alert → Guardian

---

## ✨ Key Features

* 🆘 **One-Touch SOS Activation:** Emergency alert initiated using a dedicated push button.
* 📍 **GPS Location Tracking:** Retrieves geographical coordinates using the NEO-6M GPS module.
* 📲 **Instant Telegram Notification:** Sends emergency location information to a designated guardian through a Telegram bot.
* 🗺️ **Google Maps Integration:** Generates a Google Maps link using GPS coordinates.
* 🔊 **Buzzer Indication:** Provides an audible confirmation during emergency activation.
* 🔋 **Rechargeable Power Supply:** Operates using a 3.7V Li-Po battery.
* ⌚ **Wearable Design:** Compact prototype designed to be worn on the wrist.
* 💰 **Low-Cost Implementation:** Developed using affordable and widely available electronic components.

---

## 🏗️ System Architecture

The system consists of hardware and software components working together to detect emergency activation, retrieve GPS coordinates, and transmit location information.

### Block Diagram
 ```mermaid
flowchart TD
    A([USER]) --> B[Push Button - SOS]
    B --> C[ESP32 Microcontroller]

    C --> D[GPS NEO-6M]
    C --> E[Wi-Fi]
    C --> F[Buzzer]

    D --> G[Telegram Bot]
    E --> G

    F --> H[Alert Indication]

    G --> I([Guardian])
    I --> J[Receives GPS Location]
```           
<p align="center">
</p>

### System Workflow

1. The user presses the emergency push button.
2. The ESP32 detects the button activation.
3. The NEO-6M GPS module provides latitude and longitude coordinates.
4. The ESP32 processes the received GPS information.
5. A Google Maps location link is generated.
6. The ESP32 connects to the internet through Wi-Fi.
7. The Telegram bot sends the emergency location message to the designated guardian.
8. The buzzer provides an audible confirmation.

---

## 🔧 Hardware Components

| No. | Component               | Purpose                  |
| --- | ----------------------- | ------------------------ |
| 1   | ESP32 Development Board | Main microcontroller     |
| 2   | NEO-6M GPS Module       | GPS location tracking    |
| 3   | Push Button             | Emergency activation     |
| 4   | Buzzer                  | Audible alert indication |
| 5   | 3.7V Li-Po Battery      | Power supply             |
| 6   | Connecting Wires        | Electrical connections   |

<p align="center">
</p>

The ESP32 acts as the central processing unit, coordinating GPS communication, button detection, and Wi-Fi-based message transmission.

---

## 💻 Software & Technologies

| Technology           | Application                    |
| -------------------- | ------------------------------ |
| Arduino IDE          | ESP32 programming              |
| Embedded C/C++       | Firmware development           |
| ESP32 Wi-Fi          | Internet connectivity          |
| TinyGPS++            | GPS data parsing               |
| UniversalTelegramBot | Telegram bot communication     |
| Telegram Bot API     | Emergency message transmission |
| UART                 | ESP32-GPS communication        |

### Communication Protocols

* **UART:** Communication between ESP32 and GPS NEO-6M.
* **Wi-Fi:** Internet connectivity for sending emergency messages.
* **Telegram Bot API:** Transmission of GPS location information to the guardian.

---

## 🔌 Circuit Connections

The following connections were used during hardware implementation.

| Component   | Connection           |
| ----------- | -------------------- |
| GPS TX      | ESP32 RX             |
| GPS RX      | ESP32 TX             |
| Push Button | ESP32 Digital Input  |
| Buzzer      | ESP32 Digital Output |
| Battery     | Power Supply         |

*Refer to the circuit diagram for the complete hardware connection details.*

<p align="center">
</p>

---

## 📲 Telegram Emergency Alert

The Telegram bot is used to communicate emergency location information to the designated guardian.

When the SOS button is pressed, the system generates a Google Maps link using the GPS coordinates and transmits it through Telegram.

**Example message format:**

```text
🚨 EMERGENCY ALERT!

An SOS alert has been triggered.

📍 Location:
Latitude: XX.XXXXXX
Longitude: XX.XXXXXX

🗺️ Google Maps Location:
https://maps.google.com/?q=LATITUDE,LONGITUDE

Please check immediately!
```

<p align="center">
</p>

---

## 🧪 Testing & Performance Evaluation

The developed prototype was tested under different operating conditions to evaluate its functionality and reliability.

### 1. GPS Accuracy and Response Time

* GPS location acquisition was tested under outdoor conditions.
* Initial satellite acquisition delay was observed.
* Location retrieval response was evaluated after SOS activation.

### 2. Stress Testing

* The device was tested during continuous operation.
* ESP32 and GPS communication stability were verified.

### 3. Reliability Testing

* Consistent device operation was observed after stable GPS satellite acquisition.
* Location updates were reliable under clear-sky conditions.
* No major communication failures were observed during testing.

---

## ⚙️ Challenges & Engineering Decisions

| Challenges                      | Engineering Decisions                   |
| ------------------------------- | --------------------------------------- |
| GPS satellite acquisition delay | Used NEO-6M GPS module                  |
| Power supply stability          | Integrated a rechargeable Li-Po battery |
| UART communication reliability  | Used serial communication               |
| GPS data interpretation         | Implemented TinyGPS++ library           |
| Internet communication          | Utilized ESP32 built-in Wi-Fi           |

---

## 🚀 Future Improvements

Although the prototype successfully demonstrates emergency location sharing, several improvements can enhance its functionality and real-world usability.

* **GSM Integration:** Add SMS-based emergency notifications.
* **Mobile Application:** Develop a dedicated application for monitoring and emergency management.
* **Multiple Emergency Contacts:** Enable notifications to multiple guardians.
* **Miniaturized PCB:** Design a compact custom PCB.
* **Waterproof Enclosure:** Improve durability and usability.
* **Emergency Service Integration:** Explore integration with authorized emergency response services.
* **Improved Power Management:** Optimize battery consumption for longer operating time.

---

## 🌍 Applications

The Smart Wearable Safety Band can be useful for:

* Women travelling alone.
* College students.
* Elderly individuals.
* Night-shift employees.
* Individuals requiring personal safety assistance.
