

## [Z-Bee Duo](https://gio-dot.github.io/Z-Bee-Duo/)/LAN Coordinator

1.	If not yet present, open Z-Bee case and insert the LAN module.
2.	Power on Z-Bee (i.e. with a cellular charger using a male to female type A usb cable or an USB-C cable, **do not power by a PC/Raspberry USB port when used as LAN adapter**). Connect an ethernet cable.
3.	After a while Z-Bee lan will connect to your LAN (its default setting is DHCP); once connected, check Z-Bee IP address in router settings or using apps like Fing. It is recommended to set a static IP for Z-Bee; this can be done in your router settings. Image below show how Z-Bee Lan interface appears in the LAN:
<p float="left">
  <img src="https://github.com/Gio-dot/Z-Bee-Duo/blob/main/images/photo_2021-12-27_22-26-27.jpg?raw=true" width="400" /> 
</p>


## Zigbee2mqtt configuration

Please follow general zigbee installation instructions [here](https://gio-dot.github.io/Z-Bee-Duo/usb-coordinator). Once installed do not use usb port in "serial" path: use Z-Bee ip address instead as shown in the image below (remember to add the :23 port at the end of the ip address):

<p float="left">
  <img src="https://github.com/Gio-dot/Z-Bee-Duo/blob/main/images/Zigbee2mqtt+Esp-Link+Esp-01s+Z-Bee%20Duo.png?raw=true" width="500" /> 
</p>

**NOTE:**

If Z-Bee was previously used as USB adapter, the new configuration will maintain all previous settings (no need to repair etc.).

