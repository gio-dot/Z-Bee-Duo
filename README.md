# Z-Bee Duo
The first **HYBRID ZIGBEE ADAPTER**: can be used both as **usb stick** and as **Raspberry hat** with no modifications!

<img src="https://github.com/Gio-dot/Z-Bee-Duo/blob/main/images/20210319_115743.jpg?raw=true" width="800">

**Z-Bee Duo** is the first zigbee adapter that can be used as a **normal coordinator USB stick** (connected to an host where home automation software like Home assistant is installed), or as a **Raspberry PI Zero hat** (for Raspberry PI Zero only: it is designed with its exact same dimensions). It is provided with SMA external antenna connector and USB connector.

Coupled with PI Zero W, **the most compact and powerful standalone zigbee coordinator hub** can be realized. Z-Bee Duo power coupled Raspberry through its USB connector, and thanks to the innovative design, can be plugged to a cellular charger and moved anywhere in the home.

This adapter is designed with the **new generation CC2652** Texas Instruments chip, in the most powerful version -P (+20dB embedded RF amplifier). It represent an upgrade of previous CC2530/CC2538/CC2538+CC2592 in terms of processor, ram and support. Latest Z-Stack 3.x.0 is used, and unlike its predecessor CC2538, it is fully supported by official Texas Instruments SDK.


- [Mechanical](#mechanical)
- [How to flash](#how-to-flash)
- [How to setup PI Zero example](#How-to-setup-PI-Zero-example)

***Assembled and tested Z-Bee Duo [can be found here](https://www.tindie.com/products/23046/).***

## Mechanical

Z-Bee Duo is provided with a 3 pieces case:
- part n.1 + part n.2 are used with **Raspberry PI Zero** + **Z-Bee Duo combination** (standalone zigbee2mqtt hub). In this configuration also provided spacers A and B should be used (with 2 screws on Raspberry side only).
- part n.1 + part n.3 are used with **Z-Bee Duo only** (USB stick).

<p float="left">
  <img src="https://github.com/Gio-dot/Z-Bee-Duo/blob/main/images/20210312_125742.jpg?raw=true" width="295" /> 
  <img src="https://github.com/Gio-dot/Z-Bee-Duo/blob/main/images/20210321_205527.jpg?raw=true" width="300" /> 
  <img src="https://github.com/Gio-dot/Z-Bee-Duo/blob/main/images/20210321_203024.jpg" width="300" />
</p>

## How to flash

CC2652P chip is provided with a serial bootloader, so if internal firmware have to be updated, no external programmers are needed. Flash can be done both from USB and from serial (when connected as a Raspberry hat). Take care to use a new firmware provided with serial bootloader to not loose bootloader functionality.

Tested succesfully firmwares are: 
- [Koenkk 3.x.0](https://github.com/Koenkk/Z-Stack-firmware/blob/master/coordinator/Z-Stack_3.x.0/bin/CC1352P2_CC2652P_other_coordinator_20210120.zip)
- [Egony 3.x.0](https://github.com/egony/cc2652p_E72-2G4M20S1E/blob/master/firmware/coordinator/CC2652P_E72_20210319.zip)

### FLASH USING LINUX (ie FROM RASPBERRY)

Turn off Raspberry, disconnect from power, open the enclosure to reach RESET and FLASH buttons; turn on and do the following:

- Install pyserial to enable Raspberry serial coomunication with flash tool:
```
pip install pyserial
```

- Install IntelHex package to permit firmware .hex files use:
```
pip install intelhex
```

- Download flash tool:
```
wget -O cc2538-bsl.zip https://codeload.github.com/JelmerT/cc2538-bsl/zip/master && unzip cc2538-bsl.zip    
            
```            

- Download and unpack new firmware to flash, use desired firmware github path, for example:
```
cd ~/cc2538-bsl-master
```
```
wget https://github.com/Koenkk/Z-Stack-firmware/raw/master/coordinator/Z-Stack_3.x.0/bin/CC1352P2_CC2652P_other_coordinator_20210120.zip
```
```
unzip CC1352P2_CC2652P_other_coordinator_20210120.zip
```
- Stop Zigbee2mqtt service if it is running.

- Press FLASH + RESET: release RESET before then FLASH; adapter is now in flash mode.

- Run flash using effective serial port (PORT) and previously downloaded firmware name (FIRMWARE):
```
python3 cc2538-bsl.py -p /dev/ttyAMA0 -evw CC1352P2_CC2652P_other_coordinator_20210120.hex
```

- Reboot

### FLASH FROM WINDOWS 10 (USB CONNECTED to the PC, no Raspberry connected)

- Install Python: https://www.python.org/downloads/. Verify installation with command (from Windows Powershell):
```
python -V
```
- From Windows Powershell execute:
```
python -m pip install --upgrade pip
```
```
python -m pip install pyserial
```
```
python -m pip install intelhex
```
- Download and unpack (in a folder of your choice, for example c:\python) JelmerT: https://github.com/JelmerT/cc2538-bsl.
- Download in that same folder also the new firmware to flash (for example CC1352P2_CC2652P_other_coordinator_20210120.hex). 
- Now plug USB stick. Press FLASH + RESET: release RESET before then FLASH; adapter is now in flash mode.
- From Windows powershell move to firmware folder (for example cd C: then CD python) and use this command (take care to use effective COM port and firmware name): 
```
python.exe cc2538-bsl.py -p COM4 -evw CC1352P2_CC2652P_other_coordinator_20210120.hex

```
- Done

<p float="left">
  <img src="https://github.com/Gio-dot/Z-Bee-Duo/blob/main/images/Flash%20W10-1.png?raw=true" width="500" /> 
  <img src="https://github.com/Gio-dot/Z-Bee-Duo/blob/main/images/Flash%20W10-2.png?raw=true" width="400" /> 
</p>

### HOW TO SETUP PI ZERO EXAMPLE

Please follow this steps to setup a standalone zigbee2mqtt server with a Raspberry PI Zero W and Z-Bee Duo:
- Install Raspberry SO (via the Raspberry Pi Imager, suggested Raspberry Pi OS Lite (32-bit): https://projects.raspberrypi.org/en/projects/raspberry-pi-setting-up/2
- Tune Raspberry PI Zero settings (instructions are the same for Z-Bee Duo): https://www.zigbee2mqtt.io/information/connecting_cc2530.html#to-a-raspberry-pi-zero
- Install zigbee2mqtt (venv mode): https://www.zigbee2mqtt.io/information/virtual_environment.html
- Edit zigbee2mqtt configuration before to start it: https://www.zigbee2mqtt.io/getting_started/running_zigbee2mqtt.html#3-configuring


Zigbee2mqtt configuration file example on Raspberry PI Zero:
```
homeassistant: true
permit_join: true
mqtt:
  base_topic: zigbee2mqtt
  # MQTT server URL (your homeassistant host IP address)
  server: 'mqtt://192.168.1.3:1883'
  # MQTT server authentication, uncomment if required:
  # user: my_user
  # password: my_password
serial:
  port: /dev/ttyAMA0
frontend:
  port: 8080
experimental:
  new_api: true
  transmit_power: 15
advanced:
  log_level: info
  pan_id: 6754
  channel: 11
  
 ```



