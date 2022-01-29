
## [Z-Bee Duo](https://gio-dot.github.io/Z-Bee-Duo/)/Usb Coordinator

The first step before to use a zigbee coordinator is to choose the way to integrate it in your Home automation software (Homeassistant). There are 2 main way: the most used and complete, compatible and flexible way is zigbee2mqtt, the easiest way is the native homeassistant zigbee integration called ZHA:

## Zigbee2mqtt installation:

- #### [Installation guide](https://www.zigbee2mqtt.io/getting_started/running_zigbee2mqtt.html)

- [Specific WiFi version setup](https://gio-dot.github.io/Z-Bee-Duo/wifi-coordinator)
- [Specific Lan version setup](https://gio-dot.github.io/Z-Bee-Duo/lan-coordinator)


### !!!! NOTE, PLEASE READ !!!!!

- **Serial Device Path**: Remember that in most cases Z-Bee duo usb path is: **```/dev/ttyUSB0```**

## ZHA setup:

- #### [ZHA setup guide](https://www.home-assistant.io/integrations/zha/#configuration---gui)

### !!!! NOTE, PLEASE READ !!!!!

- **Serial Device Path**: Remember that in most cases Z-Bee duo usb path is: **```/dev/ttyUSB0```**
- **ZHA radio type Device**: choose **```znp Texas Instruments (e.g., CC253x, CC26x2, CC13x2)```** for Z-Bee Duo

## Italian language guides:

[Installazione Zigbee2mqtt hassio](https://indomus.it/guide/come-installare-e-configurare-zigbee2mqtt-su-home-assistant-hassio/)

[Installazione Zigbee2mqtt raspbian](https://indomus.it/guide/come-installare-e-configurare-zigbee2mqtt-su-raspbian-di-raspberry-pi/)

[Installazione Zigbee2mqtt docker](https://indomus.it/guide/come-installare-e-configurare-zigbee2mqtt-con-docker-su-raspbian-di-raspberry-pi/)


