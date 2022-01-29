## [Z-Bee Duo](https://gio-dot.github.io/Z-Bee-Duo/)/WiFi Coordinator

<p float="left">
  <img src="https://github.com/Gio-dot/Z-Bee-Duo/blob/main/images/20210415_112758.jpg?raw=true" width="425" /> 
  <img src="https://github.com/Gio-dot/Z-Bee-Duo/blob/main/images/20210415_113334.jpg?raw=true" width="425" /> 
</p>

1.	Open Z-Bee case and insert Wifi module as in the picture above.
2.	Power Z-Bee (i.e. with a cellular charger, **do not insert in a PC/Raspberry USB port when used as ser2net adapter**).
3.	Wifi module now create an Access point because it is not connected to home wifi: connect to that AP (be sure that DHCP is enabled on your computer) and open module Webpage to connect it to your wifi. Address is 192.168.4.1.
<p float="left">
  <img src="https://github.com/Gio-dot/Z-Bee-Duo/blob/main/images/Settings.png?raw=true" width="350" /> 
  <img src="https://github.com/Gio-dot/Z-Bee-Duo/blob/main/images/CaptivePortalLogin.png?raw=true" width="350" /> 
</p>
4.	Once connected to your wifi, check Z-Bee IP address in router settings or using apps like Fing. It is recommended to set a static IP for Z-Bee; this can be done in your router settings.

## Zigbee2mqtt setup

Once Z-Bee Duo wifi is connected to wifi network, its ip address have to be set in zigbee2mqtt configuration file as in the picture below:

- Stop zigbee2mqtt.
- Open zigbee2mqtt configuration file and edit serial port as shown.
- Start zigbee2mqtt.
**NOTE**
If Z-bee was previously used as USB adapter, the new configuration will maintain all previous settings (no need to repair etc.).

<p float="left">
  <img src="https://github.com/Gio-dot/Z-Bee-Duo/blob/main/images/Zigbee2mqtt+Esp-Link+Esp-01s+Z-Bee%20Duo.png?raw=true" width="500" /> 
</p>

## ZHA setup

Once Z-Bee Duo wifi is connected to wifi network, during ZHA initial setup its ip address have to be set in ZHA **Serial device path** as shown:

```socket://[IP]:[PORT]``` for example ```socket://192.168.1.11:23```

**NOTE**

If Z-Bee Duo was previously used as USB adapter, to migrate to a WiFi or Lan solution follow these steps:

- Delete the whole ZHA integration from Homeassistant settings. **Note that the devices already paired wil be mainteined in ZHA configuration !!!**
- Add again ZHA integration using ip/port address as shown above this time.
- **The new configuration will maintain all previous settings (no need to repair etc.).**



