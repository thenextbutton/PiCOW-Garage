# 🏡 PiCOW Garage: Home Assistant ESPHome Garage Door Opener

[![Raspberry Pi Pico W](https://img.shields.io/badge/Raspberry%20Pi-Pico%20W-red?logo=raspberry-pi&logoColor=white)](https://www.raspberrypi.com/products/raspberry-pi-pico/)
[![ESPHome 2024.12.4+](https://img.shields.io/badge/ESPHome-2024.12.4+-2097e3?logo=esphome&logoColor=white)](https://esphome.io/)
![Apple CarPlay](https://img.shields.io/badge/Apple-CarPlay-silver?logo=apple&logoColor=white)
[![GitHub last commit](https://img.shields.io/github/last-commit/thenextbutton/PiCOW-Garage)](https://github.com/thenextbutton/PiCOW-Garage/commits/main)
[![GitHub Issues](https://img.shields.io/github/issues/thenextbutton/PiCOW-Garage)](https://github.com/thenextbutton/PiCOW-Garage/issues)
[![GitHub Pull Requests](https://img.shields.io/github/issues-pr/thenextbutton/PiCOW-Garage)](https://github.com/thenextbutton/PiCOW-Garage/pulls)
[![GitHub Stars](https://img.shields.io/github/stars/thenextbutton/PiCOW-Garage?style=social)](https://github.com/thenextbutton/PiCOW-Garage/stargazers)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://github.com/thenextbutton/PiCOW-Garage/blob/main/LICENSE)

---
This project demonstrates how to integrate a **Raspberry Pi Pico W** with **Home Assistant ESPHome** to create a smart garage door opener. It's a fun exploration of custom hardware and smart home automation! 

---

## 📖 Table of Contents

* [Project Overview](#-project-overview)
* [Hardware Components](#-hardware-components)
* [Configuration Changes](-#configuration-changes)
* [Home Assistant Integration](#-home-assistant-integration)
* [Apple CarPlay Integration](#-apple-carplay-integration)
* [Work in Progress](#-work-in-progress)
* [Contributing](#-contributing)
* [License](#-license)

---

## 🔭 Project Overview

<img src="https://github.com/thenextbutton/PiCOW-Garage/assets/64163980/6de8b010-c67c-4f27-8822-ed3e0d929126" alt="PiCOW Garage Logo" width="225" height="225"><br>
This project is my personal exploration into custom hardware and home automation, specifically detailing the integration of a **Raspberry Pi Pico W** into **Home Assistant ESPHome** for use as a smart garage door opener.


---

## 🛒 Hardware Components

Here's a list of the components used in this project:

**Core Electronics:**
* 1 x **Raspberry Pi Pico W** 
* 1 x **FREENOVE Breakout Board** for Raspberry Pi Pico W
* 1 x **4.7K Ohm resistor**
* 2 x **DS18B20 Digital Temperature Sensor** 
* 1 x **Ultrasonic Distance Sensor HC-SR04** 
* 1 x **OLED SSD1306** (Work in progress) 
* 1 x **6mm Oxidized Black LED Metal** (3-6v Green) 

**Wiring & Connectors:**
* 3 x **Wago Splicing Connectors** with Levers (221 Series - 3 Conductor)
* 1 x **Right angle micro USB cable**
* **5 core cable** (length depends on distance to control box)
* **4 core cable** (length depends on distance to garage door motor)
* **4 Kynar wires** (for HC-SR04 to PiCOW)

**Enclosure & Mounting:**
* 1 x **British General IP55 weatherproof outdoor enclosure** (180MM X 99MM X 111MM) 
* 2 x **British General plastic cable gland 20mm**
* 1 x **British General plastic cable gland 25mm**
* 4 x **M2 Nylon standoffs**
* 4 x **M2 Nylon screws**
* 4 x **M2 Nylon washers**
* 4 x **M2 Nylon bolts**

**Tools:**
* 1 x **2mm Drill bit** 
* 1 x **Countersink Drill bit**

**Control Box Components:**
* 1 x **Waterproof button box 22mm** (4 hole)
* 2 x **22mm Momentary button arrow** (black background, white arrow) (LA38A-11BN) 
* 1 x **22mm Self-Locking Red Emergency push button** (LA38A-11ZS) 
* 1 x **22mm 2-position rotating switch** (LA38-11x/21) 

---

## ⚙️ Configuration Changes

Before deploying the code, you'll need to modify the following substitutions within the ESPHome configuration file. These are crucial for your device's unique setup and security.

```yaml
# --- ESPHome Substitutions ---
# Change these values to match your specific setup.
# -----------------------------
substitutions:
  devicename: picow_garage         # Your desired device name
  friendlyname: PiCOW_Garage       # A friendly name for Home Assistant

  # These define the credentials for the Access Point (AP) the PiCOW will create
  # if it cannot connect to your primary Wi-Fi network. This acts as a fallback
  # for initial setup or troubleshooting.
  fallback_ssid: "<<ap_ssid_name>>" # The SSID for the fallback Access Point
  fallback_ssid_password: "<<ap_ssid_password>>" # The password for the fallback Access Point
  
  api_encryption_key: "<<api_encryption>>" # Your ESPHome API encryption key
  ota_password: "<<ota_password>>"     # OTA (Over-The-Air) update password
```

 Note: Replace the placeholder values (<<...>>) with your actual network credentials and security keys.

---

## 🏡 Home Assistant Integration
Running the ESPHome code as is will automatically create the following controls and sensors on your default Home Assistant dashboard, providing immediate access to your garage door's status and controls:<br>
![Screenshot of a Home Assistant garage door entities.](https://github.com/thenextbutton/PiCOW-Garage/blob/main/_readme_images/home_assistant_garage_area_overview.png?raw=true)

Default Dashboard Entities
Device Configuration & Diagnostics
In the Home Assistant Devices section, you'll find comprehensive configuration and diagnostic information for your PiCOW Garage device:<br>
![Screenshot of a Home Assistant garage door entities.](https://github.com/thenextbutton/PiCOW-Garage/blob/main/_readme_images/home_assistant_garage_config_diagnostic.png?raw=true)<br><br>

---

## 🚗 Apple CarPlay Integration
If you use Apple CarPlay, you can publish the garage door cover entity to HomeKit via Home Assistant. This allows you to display the garage door controls directly in CarPlay when your car is near your home location. Ensure Siri Suggestions is enabled for this feature to work.

Siri Suggestions in Dashboard
Garage Door Controls in CarPlay
Here's how the garage door controls appear in Apple CarPlay, showing both open and closing states:<br>
![Screenshot of Siri Suggesstions in Dashboard.](https://github.com/thenextbutton/PiCOW-Garage/blob/9af56f3565fba93c72edb1e208e576e03d3eb1d9/_readme_images/Siri_Suggestions_in_Dashboard.PNG?raw=true)<br><br>

Garage Door Open:<br>
![Screenshot of Garage Door OPEN in Dashboard.](https://github.com/thenextbutton/PiCOW-Garage/blob/main/_readme_images/CarPlay_Garage_Door_Open.PNG?raw=true)<br><br>

Garage Door Closing:<br>
![Screenshot of Garage Door CLOSING in Dashboard.](https://github.com/thenextbutton/PiCOW-Garage/blob/main/_readme_images/CarPlay_Garage_Door_Closing.PNG?raw=true)<br><br>

---

## ✨ Work in Progress
This project is continuously evolving! Here are some features currently under active development or planned for future implementation:

OLED SSD1306 Display Integration: Work is ongoing to fully integrate the OLED SSD1306 display for real-time status updates directly on the device.

---

## 🤝 Contributing
Feel free to open an issue or submit a pull request if you have suggestions for improvements or encounter any bugs. Your contributions are welcome!

---

## 📄 License

This project is licensed under the MIT License.
