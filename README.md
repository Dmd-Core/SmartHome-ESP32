<div align="center">

  <img src="images/Logo.png" width="180" alt="dmd-core-logo" />
  
  # Smart Home IoT System
  **Architected & Developed by dmd-core**

![ESP32](https://img.shields.io/badge/ESP32-IoT-blue)
![Blynk](https://img.shields.io/badge/Blynk-Cloud-green)
![Arduino](https://img.shields.io/badge/Arduino-C++-00979D)
![Wokwi](https://img.shields.io/badge/Wokwi-Simulation-orange)
![License](https://img.shields.io/badge/License-MIT-red)
</div>

A complete IoT-based Smart Home Automation System built using **ESP32**, **Blynk Cloud**, and **Wokwi Simulator**.

This project demonstrates how modern Internet of Things (IoT) technologies can be used to remotely control household appliances through a cloud-based infrastructure. The system provides real-time control over lighting, heating, and cooling devices using an ESP32 microcontroller connected to the Blynk IoT platform.

The entire project is fully simulated using Wokwi, allowing development, testing, and demonstration without requiring physical hardware.

---

# 📚 Table of Contents

* Project Overview
* Key Features
* System Architecture
* Technology Stack
* Hardware Components
* Software Requirements
* Pin Configuration
* Circuit Design
* Project Structure
* Installation Guide
* Blynk Setup
* Wokwi Simulation
* Source Code Explanation
* Working Principle
* Testing Procedure
* Troubleshooting
* Security Notice
* Future Improvements
* Project Report
* Documentation Gateway
* Author
* License
* Acknowledgements

---

# 📌 Project Overview

The purpose of this project is to create a simple yet scalable smart home automation system capable of remotely controlling household devices through the internet.

The system consists of:

* ESP32 Microcontroller
* Blynk IoT Cloud Platform
* Mobile Dashboard Interface
* Simulated Smart Home Appliances

Three primary home functions are controlled:

* 💡 Lighting System
* 🔥 Heating System
* ❄️ Cooling System

The user interacts with the system through the Blynk mobile application. Commands are sent to the Blynk Cloud and then forwarded to the ESP32 via WiFi.

---

# ✨ Key Features

* Remote device control through smartphone
* Real-time cloud communication
* ESP32 WiFi connectivity
* Blynk Cloud integration
* Modular firmware architecture
* Expandable smart home framework
* Virtual hardware simulation using Wokwi
* Beginner-friendly implementation
* Educational IoT project
* Scalable design for future upgrades

---

# 🏗 System Architecture

```text
User
 │
 ▼
Blynk Mobile App
 │
 ▼
Blynk Cloud
 │
 ▼
ESP32
 ├── Lighting System
 ├── Heating System
 └── Cooling System
```

### Data Flow

1. User presses a button in the Blynk mobile application.
2. Command is sent to Blynk Cloud.
3. Blynk Cloud communicates with ESP32.
4. ESP32 receives the command.
5. Corresponding GPIO output changes state.
6. Connected device is activated or deactivated.

---

# 🛠 Technology Stack

| Category               | Technology        |
| ---------------------- | ----------------- |
| Microcontroller        | ESP32             |
| Programming Language   | C++               |
| Development Framework  | Arduino Framework |
| IoT Platform           | Blynk Cloud       |
| Connectivity           | WiFi              |
| Simulation Environment | Wokwi             |
| Version Control        | Git               |
| Repository Hosting     | GitHub            |

---

# 🔧 Hardware Components

| Component               | Quantity |
| ----------------------- | -------- |
| ESP32 Development Board | 1        |
| LED                     | 3        |
| 220Ω Resistor           | 3        |
| Jumper Wires            | Several  |

---

# 💻 Software Requirements

Before starting, install the following tools:

* Arduino IDE
* ESP32 Board Package
* Blynk Library
* Wokwi Account
* Blynk Mobile Application
* Git (Optional)

---

# 📍 Pin Configuration

| Device          | GPIO Pin |
| --------------- | -------- |
| Lighting System | GPIO 23  |
| Heating System  | GPIO 22  |
| Cooling System  | GPIO 21  |

---

# 🔌 Circuit Design

Each appliance is represented by an LED during simulation.

### Lighting System

GPIO23 → Resistor → LED → GND

### Heating System

GPIO22 → Resistor → LED → GND

### Cooling System

GPIO21 → Resistor → LED → GND

---

# 📸 Project Images

## Circuit Diagram

<img src="images/circuit.png" width="180" alt="dmd-core-logo" />

## Blynk Dashboard

Place your dashboard screenshot here:

<img src="images/dashboard.png" width="180" alt="dmd-core-logo" />

---

# 📂 Project Structure

```text
Smart-Home-IoT/
│
├── sketch.ino
├── diagram.json
├── libraries.txt
├── README.md
│
├── docs/
│   └── IoT.pdf
│
└── images/
    ├── circuit.png
    ├── dashboard.png
    └── simulation.png
```

---

# 🚀 Installation Guide

## Step 1: Install Arduino IDE

Download and install Arduino IDE from the official website.

---

## Step 2: Install ESP32 Board Package

Open:

Tools → Board Manager

Search:

ESP32

Install the latest stable release.

---

## Step 3: Install Blynk Library

Open:

Library Manager

Search:

Blynk

Install the latest version.

---

## Step 4: Clone Repository

```bash
git clone https://github.com/YOUR_USERNAME/Smart-Home-IoT.git
```

---

## Step 5: Open Project

Open:

```text
sketch.ino
```

inside Arduino IDE.

---

## Step 6: Configure Credentials

Replace the placeholders with your own credentials.

```cpp
#define BLYNK_TEMPLATE_ID   "YOUR_TEMPLATE_ID"
#define BLYNK_TEMPLATE_NAME "Smart Home"
#define BLYNK_AUTH_TOKEN    "YOUR_AUTH_TOKEN"

char ssid[] = "YOUR_WIFI_NAME";
char pass[] = "YOUR_WIFI_PASSWORD";
```

---

## Step 7: Upload Firmware

Select:

```text
ESP32 Dev Module
```

Upload the code to your ESP32.

---

# ☁️ Blynk Setup

## Create Template

1. Login to Blynk Console
2. Create New Template
3. Select ESP32
4. Connection Type: WiFi

---

## Create Datastreams

| Datastream | Virtual Pin |
| ---------- | ----------- |
| Lamp       | V0          |
| Heating    | V1          |
| Cooling    | V2          |

---

## Create Dashboard

Add three Switch widgets.

### Widget 1

Lamp Control

Virtual Pin: V0

### Widget 2

Heating Control

Virtual Pin: V1

### Widget 3

Cooling Control

Virtual Pin: V2

---

# 🖥 Wokwi Simulation

The project can be tested entirely inside Wokwi.

Steps:

1. Open Wokwi
2. Import project files
3. Start simulation
4. Connect to Blynk Cloud
5. Control devices remotely

---

# ⚙️ Source Code Explanation

## Lamp Control

```cpp
BLYNK_WRITE(V0)
{
    int state = param.asInt();
    digitalWrite(LAMP_PIN, state);
}
```

Controls the lighting system.

---

## Heating Control

```cpp
BLYNK_WRITE(V1)
{
    int state = param.asInt();
    digitalWrite(HEATING_PIN, state);
}
```

Controls the heating system.

---

## Cooling Control

```cpp
BLYNK_WRITE(V2)
{
    int state = param.asInt();
    digitalWrite(COOLING_PIN, state);
}
```

Controls the cooling system.

---

# 🔄 Working Principle

1. ESP32 connects to WiFi.
2. ESP32 connects to Blynk Cloud.
3. User sends command through mobile application.
4. Blynk Cloud forwards command.
5. ESP32 updates GPIO state.
6. Appliance responds immediately.

---

# 🧪 Testing Procedure

### Test 1

Turn ON Lighting.

Expected Result:

Lighting LED turns ON.

---

### Test 2

Turn ON Heating.

Expected Result:

Heating LED turns ON.

---

### Test 3

Turn ON Cooling.

Expected Result:

Cooling LED turns ON.

---

# 🔍 Troubleshooting

## ESP32 Cannot Connect to WiFi

Check:

* SSID
* Password
* Router Connection

---

## Blynk Device Offline

Check:

* Auth Token
* Template ID
* Internet Connectivity

---

## LEDs Not Responding

Check:

* Wiring
* GPIO Pins
* Power Supply

---

# 🔒 Security Notice

Before publishing the project:

Never expose:

* WiFi Passwords
* Blynk Auth Tokens
* API Keys
* Sensitive Credentials

Always replace them with placeholders.

---

# 🚧 Future Improvements

Potential upgrades include:

* DHT22 Temperature Sensor
* Humidity Monitoring
* Automatic Climate Control
* Energy Consumption Monitoring
* Push Notifications
* Voice Assistant Integration
* Mobile Data Logging
* AI-Based Decision Making
* TinyML Deployment
* Home Security Module

---

# 📄 Project Report

The complete academic report is available in:

![System Diagram](docs/IoT.pdf)

The report explains:

* Project Objectives
* IoT Concepts
* ESP32 Configuration
* Blynk Integration
* Circuit Design
* Implementation Details

---

### 🌐 Documentation Gateway
Choose your preferred language to explore the technical documentation:

* IR **[Persian Documentation](docs/README.fa.md)** — *فارسی*
* DE **[German Documentation](docs/README.de.md)** — *tysk*
---

# 👨‍💻 Author

Mohammad Hossein Almasi | [dmd-core]

Computer Engineering Student

Areas of Interest:

* Internet of Things (IoT)
* Embedded Systems
* ESP32 Development
* Artificial Intelligence
* Smart Automation Systems

GitHub:

https://github.com/YOUR_USERNAME

---

# 📜 License

This project is released under the MIT License.

You are free to:

* Use
* Modify
* Distribute
* Learn
* Build upon the project

for educational and research purposes.

---

# 🙏 Acknowledgements

Special thanks to:

* ESP32 Development Community
* Blynk IoT Platform
* Wokwi Simulation Platform
* Arduino Open Source Community

for providing the tools and resources that made this project possible.

---

## ⭐ Support

If you found this project useful:

⭐ Star the repository

🍴 Fork the project

📢 Share it with others

Thank you for visiting this project and supporting open-source learning.

<div align="center">
  <br>
  <a href="dmd.core.dev@gmail.com">
    <img src="https://img.shields.io/badge/Email-000000?style=for-the-badge&logo=gmail&logoColor=white&logoWidth=20" alt="Email" />
  </a>
</div>
