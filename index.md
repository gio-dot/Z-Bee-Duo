
The first **MODULAR 4 MODES USB ZIGBEE ADAPTER**: USB Stick / Ser2net Wifi Hub / LAN Hub / Raspberry PI Zero Hat

<img src="https://github.com/Gio-dot/Z-Bee-Duo/blob/main/images/20211010_101921-ico-3.jpg?raw=true" width="900">

#### ***Assembled and tested Z-Bee Duo [can be found here](https://www.tindie.com/products/23046/).***

| [Construction -->](https://gio-dot.github.io/Z-Bee-Duo/construction) |  [Basic USB installation -->](https://gio-dot.github.io/Z-Bee-Duo/usb-coordinator) |
| :-------------------------- | :-------------------------- |
| [**WiFi coordinator setup -->**](https://gio-dot.github.io/Z-Bee-Duo/wifi-coordinator)  | [**LAN coordinator setup -->**](https://gio-dot.github.io/Z-Bee-Duo/lan-coordinator)   |
| [**PI0 zigbee Hub -->**](https://gio-dot.github.io/Z-Bee-Duo/pi0-zigbee-hub) | [**Firmware upgrade -->**](https://gio-dot.github.io/Z-Bee-Duo/Firmware-upgrade)  |
| [**Zigbee router -->**](https://gio-dot.github.io/Z-Bee-Duo/zigbee-router) | [**FAQ -->**](https://gio-dot.github.io/Z-Bee-Duo/FAQ)  |


## **Z-Bee Duo**

Is an innovative zigbee adapter (coordinator or router) in form of usb dongle. It can be used with popular zigbee software like zigbee2mqtt, Homeassistant ZHA etc. It is designed with the new generation CC2652 Texas Instruments chip, in the most powerful version -P (+20dB embedded RF amplifier) and represents an upgrade of previous CC2530/CC2538/CC2538+CC2592 in terms of processor, ram and support. Latest Z-Stack 3.x.0 is used, and unlike its predecessor CC2538, it is fully supported by official Texas Instruments SDK.

**The unique design of the Z-Bee Duo allows to use it in 4 different ways:**

1.	**Standard USB coordinator** (connected to a host where home automation software like Home assistant is installed).

2.	**Wifi connected (ser2net) coordinator**: with the optional **wifi module** (that fit inside Z-bee case), Z-Bee Duo can be wirelessly connected to your home automation hub. In this way it can be moved away from your hub (simply powered by a cellular charger) to find the best position in the house and/or to avoid usb 3.0 Raspberry pi4 issues that in many cases affect USB connected adapters.

3.	**LAN connected coordinator**: with the optional **Ethernet module** (that fit inside Z-bee case), Z-Bee Duo can be connected to your home automation hub through an ethernet port. In this way it can be moved away from your hub (simply powered by a cellular charger) to find the best position in the house and/or to avoid usb 3.0 Raspberry pi4 issues that in many cases affect USB connected adapters.

4.	**Independent zigbee2mqtt hub**: a Raspberry PI Zero W (not included) can be coupled with Z-Bee Duo (it fits in its case); with zigbee2mqtt installed on PI Zero, the most compact and powerful standalone zigbee coordinator hub can be realized. It communicate in mqtt with home automation hub (Home assistant and others). This hub can be moved away from your hub (simply powered by a cellular charger) to find the best position in the house and/or to avoid usb 3.0 Raspberry pi4 issues that in many cases affect USB connected adapters.

**Technical features**

- CC2652P Texas Instruments ZigBee chip with embedded +20dB RF amplifier for maximum range. Ebyte or RF-Star chips are used (depending on market availability). 
- Fully tested with Z2M and ZHA
- Red and green leds for state indication.
- External SMA antenna.
- Serial bootloader. No external programmer needed to update firmware: can be done through USB port.
- Auto-BSL, no need to press buttons (although present) to update firmware.
- CH340C USB Bridge
- Plug & Play: shipped with latest Z-Stack 3.x.0 firmware and fully tested. Also wifi module is shipped fully tested and ready to use.





