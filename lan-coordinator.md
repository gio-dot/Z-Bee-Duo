

## [Z-Bee Duo](https://gio-dot.github.io/Z-Bee-Duo/)/LAN Coordinator

1.	If not yet present,open Z-Bee case and insert LAN module.
2.	Power Z-Bee (i.e. with a cellular charger using a male to female type A usb cable or a micro USB cable, **do not power by a PC/Raspberry USB port when used as LAN adapter**).
3.	Once connected to your router, check Z-Bee IP address in router settings or using apps like Fing. It is recommended to set a static IP for Z-Bee; this can be done in your router settings.
<p float="left">
  <img src="https://github.com/Gio-dot/Z-Bee-Duo/blob/main/images/photo_2021-12-27_22-26-27.jpg?raw=true" width="400" /> 
</p>

As last point we have to **set the new “serial port”** in zigbee2mqtt configuration file as in the picture below (use your Z-bee ip address):

```
- Stop zigbee2mqtt.
- Open and edit serial port in zigbee2mqtt configuration file.
- Start zigbee2mqtt.
If Z-bee was previously used as USB adapter, the new configuration will maintain all previous settings (no need to repair etc.).
```
<p float="left">
  <img src="https://github.com/Gio-dot/Z-Bee-Duo/blob/main/images/Zigbee2mqtt+Esp-Link+Esp-01s+Z-Bee%20Duo.png?raw=true" width="500" /> 
</p>


