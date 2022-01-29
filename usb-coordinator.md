
## [Z-Bee Duo](https://gio-dot.github.io/Z-Bee-Duo/)/Basic installation

The first step before to use a zigbee coordinator is to choose the way to integrate it in your Home automation software (Homeassistant). There are 2 main way: the most used and complete, compatible and flexible way is zigbee2mqtt, the easiest way is the native homeassistant zigbee integration called ZHA.
**Please read specific instructions for WiFi/Lan version before Zigbee2mqtt or ZHA setup:**
- [Specific WiFi version setup](https://gio-dot.github.io/Z-Bee-Duo/wifi-coordinator)
- [Specific Lan version setup](https://gio-dot.github.io/Z-Bee-Duo/lan-coordinator)

## Zigbee2mqtt installation

- #### [Installation guide](https://www.zigbee2mqtt.io/getting_started/running_zigbee2mqtt.html)

**NOTE**
- **Serial Device Path**: Remember that in most cases Z-Bee duo usb path is: **```/dev/ttyUSB0```**

## ZHA setup

- #### [ZHA setup guide](https://www.home-assistant.io/integrations/zha/#configuration---gui)

Setup steps:

<img src="https://github.com/Gio-dot/Z-Bee-Duo/blob/gh-pages/images/24-01-2022%2018_48_50-Greenshot.png?raw=true" width="900">



| Select port: **```/dev/ttyUSB0```** |  <img src="https://github.com/Gio-dot/Z-Bee-Duo/blob/gh-pages/images/24-01-2022%2018_49_18-Home%20Assistant%20DS220%20-%20Configurazioni%20-%20Home%20Assistant.png?raw=true" width="300"> |
| :-------------------------- | :-------------------------- |
| **Select radio type** | <img src="https://github.com/Gio-dot/Z-Bee-Duo/blob/gh-pages/images/24-01-2022%2018_49_41-Home%20Assistant%20DS220%20-%20Configurazioni%20-%20Home%20Assistant.png?raw=true" width="400">   |
| **Set port settings** | <img src="https://github.com/Gio-dot/Z-Bee-Duo/blob/gh-pages/images/24-01-2022%2019_01_14-Home%20Assistant%20DS220%20-%20Configurazioni%20-%20Home%20Assistant.png?raw=true" width="400"> |



## Italian language guides

[Installazione Zigbee2mqtt hassio](https://indomus.it/guide/come-installare-e-configurare-zigbee2mqtt-su-home-assistant-hassio/)

[Installazione Zigbee2mqtt raspbian](https://indomus.it/guide/come-installare-e-configurare-zigbee2mqtt-su-raspbian-di-raspberry-pi/)

[Installazione Zigbee2mqtt docker](https://indomus.it/guide/come-installare-e-configurare-zigbee2mqtt-con-docker-su-raspbian-di-raspberry-pi/)


