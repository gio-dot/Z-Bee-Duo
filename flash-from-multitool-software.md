## [Firmware upgrade](https://gio-dot.github.io/Z-Bee-Duo/Firmware-upgrade)/Flash with Multitool software



### USB CONNECTED to the PC, no WIFi/Lan modules or Raspberry connected to Z-Bee

Starting from Z-Bee Duo **rev.E** it is possible to flash zigbee firmware without the need to install python and press buttons. This can be done thanks to [xyzroe](https://github.com/xyzroe) flashing tool.

- Download and unpack flash tool (in a folder of your choice or in desktop), it is an executable, no need to install: [Multitool](https://github.com/Gio-dot/Z-Bee-Duo/raw/gh-pages/flash_tool/ZigStarGW-MT-x64.exe.zip)
- Download and unpack (in a folder of your choice or in desktop) the new firmware to flash (for example CC1352P2_CC2652P_other_coordinator_20210120.hex). 
- Now plug USB stick to the computer (remember to remove wifi or ethernet module if present).
- Open flash tool and locate USB port used by Z-Bee (1) and (2) fig. 1.
- Locate and select the firmware to flash (1) fig.2. Select options as in (2) fig.2 and press START (3) fig.2.
- After few seconds flash is Done!

<p float="left">
  <img src="https://github.com/Gio-dot/Z-Bee-Duo/blob/gh-pages/images/mt-fig1.jpg?raw=true" width="500" /> 
 </p>
  fig.1

<p float="left">
   <img src="https://github.com/Gio-dot/Z-Bee-Duo/blob/gh-pages/images/mt-fig2.jpg?raw=true" width="510" /> 
</p>
fig.2

