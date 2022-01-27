## [Z-Bee Duo](https://gio-dot.github.io/Z-Bee-Duo/)/Firmware upgrade

CC2652P chip is provided with a serial bootloader, so if internal firmware have to be updated, no external programmers are needed. **Flash can be done both from USB and from serial (when connected as a Raspberry hat)**. Take care to use a new firmware provided with serial bootloader to not loose bootloader functionality.

RF-Star version (blue chip): succesfully tested **coordinator** firmwares are: 
- [Koenkk 3.x.0 20211217](https://github.com/Koenkk/Z-Stack-firmware/blob/master/coordinator/Z-Stack_3.x.0/bin/CC1352P2_CC2652P_launchpad_coordinator_20211217.zip)

E-Byte version (green chip): succesfully tested **coordinator** firmwares are: 
- [Koenkk 3.x.0 20211217](https://github.com/Koenkk/Z-Stack-firmware/blob/master/coordinator/Z-Stack_3.x.0/bin/CC1352P2_CC2652P_other_coordinator_20211217.zip)
- [Egony 3.x.0 20210319](https://github.com/egony/cc2652p_E72-2G4M20S1E/blob/master/firmware/coordinator/CC2652P_E72_20210319.zip)

### FLASH WITH TEXAS INTRUMENTS FLASH PROGRAMMER 2

- Go to [this](https://www.ti.com/tool/FLASH-PROGRAMMER#primary-sw) page and download Flash Programmer 2 software.
- Install it on your computer.
- Open Flash Programmer 2 and select chip type like image below.
- Connect Z-Bee to PC usb port; **remember to remove wifi module if present!!!**
- Put Z-Bee in flash mode (Auto BSL is not supported by Flash Programmer 2 software): press FLASH + RESET: release RESET before then FLASH; adapter is now in flash mode.
- Set and flash following steps 1-6 of the image.

<p float="left">
  <img src="https://github.com/Gio-dot/Z-Bee-Duo/blob/main/images/2021-05-08%2011_23_16-SmartRF%20Flash%20Programmer%202%20-%20Texas%20Instruments.png?raw=true" width="700" /> 
</p>

### FLASH FROM LINUX (ie FROM RASPBERRY or LINUX PC)

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

- Download flash tool:
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
- Download and unpack flash tool (in a folder of your choice, for example c:\python) https://github.com/Gio-dot/Z-Bee-Duo/raw/main/flash_tool/cc2538-bsl.zip
- Download in that same folder also the new firmware to flash (for example CC1352P2_CC2652P_other_coordinator_20210120.hex). 
- Now plug USB stick. Press FLASH + RESET: release RESET before then FLASH; adapter is now in flash mode.
- From Windows powershell move to firmware folder (for example cd C: then CD python) and use this command (take care to use effective COM port and firmware name): 
```
python.exe cc2538-bsl.py -p COM4 -evw CC1352P2_CC2652P_other_coordinator_20210120.hex

```
- Since version 1.1 **adapter is provided by auto BSL**: no buttons are needed to enter il flash mode. Flash string is the following:
```
python.exe cc2538-bsl.py -p COM4 --invoke-bootloader 3 -ewv CC1352P2_CC2652P_other_coordinator_20210120.hex

```
- Done

<p float="left">
  <img src="https://github.com/Gio-dot/Z-Bee-Duo/blob/main/images/Flash%20W10-1.png?raw=true" width="500" /> 
  <img src="https://github.com/Gio-dot/Z-Bee-Duo/blob/main/images/Flash%20W10-2.png?raw=true" width="400" /> 
</p>

### FLASH VIA JTAG (in case SBL bootloader is disabled)

If serial bootloader is disabled/not present, Z-Bee Duo can be flashed through its jtag connector following this procedure that is the same for CC2652P chip
(make sure to use **CC1352P1F** chip type at point 6):
https://www.zigbee2mqtt.io/information/flashing_the_cc2538.html

