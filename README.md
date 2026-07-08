![DIY HomeLab Banner](docs/images/HomeLab.png)
![Raspberry Pi](https://img.shields.io/badge/Raspberry%20Pi-3B-C51A4A?logo=raspberrypi)
![Docker](https://img.shields.io/badge/Docker-Compose-2496ED?logo=docker)
![Home Assistant](https://img.shields.io/badge/Home%20Assistant-2026-41BDF5?logo=homeassistant)
![Matter](https://img.shields.io/badge/Matter-Supported-6C2DC7)
![License](https://img.shields.io/badge/License-MIT-green)
<h1 align="left">
--> QUICK START <--
1. Flash the IMG to a microSD card
2. Boot the Raspberry Pi
3. Open Home Assistant
4. Configure your Devices
5. Pair MatterBridge
6. Pair DIYHue (optional)
7. Pair your Matter controller
8. Enjoy.
</h1>
  
<h1 align="center">
DIY HomeLab
</h1>

**Tuya Cloud --> Home Assistant --> MatterBridge --> Smartthings/GoogleHome/Alexa**
**Tuya Cloud --> Home Assistant --> DiyHue --> Hue App/Hue Sync**
**Cameras are not integrated yet**

<h1 align="left">
  
## HARDWARE
- Raspberry Pi 3B
- ESP32 + RGB Led Strip
- Tuya Devices
- Samsung SmartThings Hub (Samsung TV)
- Google Home Mini
- Google Chromecast Built-In TV

## SOFTWARE
- Raspbery Pi OS Lite
- Docker
- Home Assistant
- MatterBridge
- DiyHue
- CastWeb API

---
# Main Goals
This project creates a universal smart home server capable of connecting devices from multiple manufacturers into a single ecosystem.
**Supported ecosystems:**
- Tuya Cloud
- Matter
- SmartThings
- Google Home
- Amazon Alexa
- Philips Hue (Emulated)
- ESPHome / ESP32
- WLED
---
# Current Devices
## Tuya
- 4x Avant Neo Smart Lamps
- NovaDigital Smart Pulse Switch
- 2x Generic Tuya Smart Switches
- Generic Tuya RGB Controller
- Positivo Casa Inteligente Camera
---
## ESP Devices
- ESP32
- WLED
- RGB5050 LED Strip
---
## Samsung (Having at least one SmartThings Hub is highly recommended)
- Samsung CU7700
- Samsung BU8000
---
# Why Home Assistant?
**Home Assistant is the heart of the project**
It receives devices from: Tuya, ESP32, WLED, Future integrations, then exports everything to: Matter, Philips Hue (Emulated)

# Why MatterBridge?
MatterBridge imports every Home Assistant entity and publishes them as Matter devices. This allows pairing with: Google Home, Alexa, SmartThings, (Mayble HomeKit and others controllers) without depending on the original manufacturer

# Why DIYHue? (DiyHue is optional)
It exists only because Samsung SmartThings, and Hue app has one feature that Matter still cannot replace: Hue Sync
Samsung SmartThings can synchronize Philips Hue lights with music, since SmartThings only supports real Philips Hue Bridges... DiyHue emulates one (Without DIYHue, everything still works) *Also work on HueSync app for Windows, i don't know if work with PhilipsSync app for Samsung TV's

**Tuya
   ↓
Home Assistant
   ↓
DIYHue
   ↓
Samsung SmartThings
   ↓
Philips Hue Sync**

---
# Docker Containers
**Current services:**
- Home Assistant
- MatterBridge
- DIYHue
- Cast-Web-API
---
# Current Limitations
- Tuya Local not configured
- Cameras are not integrated
- DIYHue is only required for Music Sync
- Raspberry Pi 3 works well but Raspberry Pi 4 is recommended
---

# Future Plans
- MQTT
- Zigbee2MQTT
- Music Assistant
- Automatic Backups
- NAS Integration
- ESPHome Devices
- Docker Compose Improvements
- Full documentation
---
# ❤️ Acknowledgements
This project would not be possible without the amazing work of the following open source communities and developers

## Home Assistant
Universal home automation platform
https://www.home-assistant.io/
## Matterbridge
Matter bridge used to expose Home Assistant devices
https://github.com/Luligu/matterbridge
## DIYHue
Philips Hue emulator used for SmartThings Music Sync
https://github.com/diyhue/diyHue
## Cast-Web-API
Google Cast REST API.
https://github.com/vervallsweg/cast-web-api
## T. Austin
Developer of the Samsung SmartThings Edge Cast-Web-API Driver.
Driver Repository: https://github.com/toddaustin07/googlecast
Without this driver, Google Home and Chromecast devices could not be integrated into SmartThings using Cast-Web-API
## WLED
ESP32 LED Controller.
https://github.com/Aircoookie/WLED
## Tuya
Cloud platform used for the current device integration.
## Docker
Container platform that makes the entire HomeLab possible.
https://www.docker.com/
## Raspberry Pi Foundation
Hardware platform used in this project.
https://www.raspberrypi.com/

# License
MIT

---
</h1>
