![DIY HomeLab Banner](docs/images/HomeLab.png)
![Raspberry Pi](https://img.shields.io/badge/Raspberry%20Pi-3B-C51A4A?logo=raspberrypi)
![Docker](https://img.shields.io/badge/Docker-Compose-2496ED?logo=docker)
![Home Assistant](https://img.shields.io/badge/Home%20Assistant-2026-41BDF5?logo=homeassistant)
![Matter](https://img.shields.io/badge/Matter-Supported-6C2DC7)
![License](https://img.shields.io/badge/License-MIT-green)
<h1 align="center">
DIY HomeLab
</h1>

**Tuya Cloud --> Home Assistant --> MatterBridge --> Smartthings/GoogleHome/Alexa**

**Tuya Cloud --> Home Assistant --> DiyHue --> Hue App/Hue Sync**

<h1 align="left">
  
## HARDWARE
|------|
| Raspberry Pi 3B |
|------|
| ESP32 + RGB Led Strip |
|------|
| Tuya Devices|
|------|
| Samsung SmartThings Hub (Samsung TV)|
|------|
| Google Home Mini |
|------|
| Google Chromecast Built-In TV|
|------|

## SOFTWARE
|------|
| Raspbery Pi OS Lite |
| Docker |
| Home Assistant |
| MatterBridge |
| DiyHue |
| CastWeb API |
|------|

# Main Goals
This project creates a universal smart home server capable of connecting devices from multiple manufacturers into a single ecosystem.

Supported ecosystems:
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
  - Living Room
  - Bedroom

- NovaDigital Smart Pulse Switch
  - Main Gate

- 2x Generic Tuya Smart Switches
  - Garage
  - Living Room LED Strip

- Generic Tuya RGB Controller
  - Bedroom Desk

- Positivo Casa Inteligente Camera

> Cameras are not integrated yet.
>
> Everything else works.

---

## ESP Devices

- ESP32
- WLED
- RGB5050 LED Strip

---

## Samsung

- Samsung CU7700
- Samsung BU8000

Having at least one SmartThings Hub is highly recommended.

---

# Architecture

```
             Tuya Cloud
                 │
                 │
          Home Assistant
        (Universal Server)
                 │
        ┌────────┴────────┐
        │                 │
 MatterBridge         DIYHue
        │                 │
        │                 │
 SmartThings        Philips Hue App
        │                 │
        └────────┬────────┘
                 │
       Google Home
                 │
             Amazon Alexa
```

---

# Why Home Assistant?

Home Assistant is the heart of the project.

It receives devices from:

- Tuya
- ESP32
- WLED
- Future integrations

Then exports everything to:

- Matter
- Philips Hue (Emulated)

This means every incompatible ecosystem becomes compatible.

---

# MatterBridge

MatterBridge imports every Home Assistant entity and publishes them as Matter devices.

This allows pairing with:

- Google Home
- Alexa
- SmartThings

without depending on the original manufacturer.

---

# Why DIYHue?

DIYHue is optional.

It exists only because Samsung SmartThings, and Hue app has one feature that Matter still cannot replace:

## Hue Sync

Samsung SmartThings can synchronize Philips Hue lights with music.

Since SmartThings only supports real Philips Hue Bridges for this feature...

DIYHue emulates one.

Result:

```
Tuya
   ↓
Home Assistant
   ↓
DIYHue
   ↓
Samsung SmartThings
   ↓
Philips Hue Sync
```

Without DIYHue:

Everything still works.

You only lose Philips Hue music synchronization. 
*Also work on HueSync app for Windows, i don't know if work with PhilipsSync app for Samsung TV's

---

# Recommended Flow

```
Tuya Cloud
      ↓
Home Assistant
      ↓
MatterBridge
      ↓
SmartThings
      ↓
Google Home
      ↓
Alexa
```

Alternative:

```
Tuya
    ↓
Home Assistant
    ↓
DIYHue
    ↓
SmartThings
```

---

# Docker Containers

Current services

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

This project would not be possible without the amazing work of the following open source communities and developers.

## Home Assistant
Universal home automation platform.
https://www.home-assistant.io/

## Matterbridge
Matter bridge used to expose Home Assistant devices.
https://github.com/Luligu/matterbridge

## DIYHue
Philips Hue emulator used for SmartThings Music Sync.
https://github.com/diyhue/diyHue

## Cast-Web-API
Google Cast REST API.
https://github.com/vervallsweg/cast-web-api

## T. Austin
Developer of the Samsung SmartThings Edge Cast-Web-API Driver.

Driver Repository:
https://github.com/toddaustin07/googlecast
Without this driver, Google Home speakers and Chromecast devices could not be integrated into SmartThings using Cast-Web-API.

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

Made with ❤️ on a Raspberry Pi 3.

</h1>
