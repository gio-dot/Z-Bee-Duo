## [Firmware upgrade](https://gio-dot.github.io/Z-Bee-Duo/Firmware-upgrade)/Flash from Linux


Turn off Raspberry, disconnect from power, open the enclosure to reach RESET and FLASH buttons; this procedure can be done both with Z-Bee connected to PC/Raspberry USB port or connected to a Raspberry as hat (remember to adapt serial port in flash string). 

If Z-Bee is connected to Raspberry/PC usb port **remember to remove wifi module if present!!!**. 

Turn on and do the following:

- Install pyserial to enable Raspberry serial coomunication with flash tool:
```
pip install pyserial
```

- Install IntelHex package to permit firmware .hex files use:
```
pip install intelhex
```

- Download flash tool
```
wget -O cc2538-bsl.zip https://github.com/Gio-dot/Z-Bee-Duo/raw/main/flash_tool/cc2538-bsl.zip && unzip cc2538-bsl.zip    
            
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

- Since version 1.1 **adapter is provided by auto BSL**: no buttons are needed to enter il flash mode. Flash string is the following:
```
python.exe cc2538-bsl.py -p /dev/ttyAMA0 --invoke-bootloader 3 -ewv CC1352P2_CC2652P_other_coordinator_20210120.hex

```

- Reboot


