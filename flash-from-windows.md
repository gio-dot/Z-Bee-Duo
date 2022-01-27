## [Z-Bee Duo](https://gio-dot.github.io/Z-Bee-Duo/)/Flash from Windows



### USB CONNECTED to the PC, no WIFi/Lan modules or Raspberry connected to Z-Bee

- Install Python: [Python](https://www.python.org/downloads/). Verify installation with command (from Windows Powershell):
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
- Download and unpack flash tool (in a folder of your choice, for example c:\python) [Flash tool](https://github.com/Gio-dot/Z-Bee-Duo/raw/main/flash_tool/cc2538-bsl.zip)
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


