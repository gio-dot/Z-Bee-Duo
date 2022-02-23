## [Z-Bee Duo](https://gio-dot.github.io/Z-Bee-Duo/)/PI0 zigbee Hub


Please follow this steps to setup a standalone zigbee2mqtt server with a **Raspberry PI Zero W** and **Z-Bee Duo**:
- Install Raspberry SO (via the Raspberry Pi Imager, suggested Raspberry Pi OS Lite (32-bit): [Raspberry PI setup](https://projects.raspberrypi.org/en/projects/raspberry-pi-setting-up/2)
- Tune Raspberry PI Zero settings (instructions are the same for Z-Bee Duo): [PI0 settings](https://www.zigbee2mqtt.io/guide/adapters/flashing/connecting_cc2530.html#to-a-raspberry-pi-zero)
- Install zigbee2mqtt (venv mode): [Zigbee2mqtt venv](https://www.zigbee2mqtt.io/information/virtual_environment.html) or in docker [Zigbee2mqtt docker](https://www.zigbee2mqtt.io/guide/installation/02_docker.html#creating-the-initial-configuration)
- Edit zigbee2mqtt configuration before to start it: [Configuration](https://www.zigbee2mqtt.io/guide/configuration/)


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
advanced:
  log_level: info
  pan_id: 6754
  channel: 11
  
 ```


