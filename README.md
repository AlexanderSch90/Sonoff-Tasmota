## 4.1.3c (Patchlevel1)
- Added support for 8 channel DIO board PCF8574. Multiple boards up to 8 are allowed. The I2C adress is changed though
  pins on the board. Up to 64 relays can be now directly adressed. Special configuration menue for PCF8574. Relays can be INVERTED
  Known issue:
  - Ports can also be used as INPUT pin and change to LOW triggered the TriggerPin on the board. NOT IMPLEMENTED yet
  - MQTT STATUS Message exceet allowed length if many relays defined. Anyhow MQTT is supported.
  - Friendlyname (Wemos, Hue) get populated but is not supported for more than 4 relays.
  - Inverted relays flicker when physically off and one other relay change (PCF8574 issue)
  - Webserverpage gets "crowded" on more than 8 relays, but work
  - Webserverpages and MQTT with TLS can rise memory problems because of amount of contend. Disable MQTT temporary
  - Configuration of PCF8574 not supported though MQTT or COMMAND. ONLY web.
  
 Troubleshooting:
  - Wire up SDA and SCL accordingly
  - Enable PCF8574 by uncomment in user_cofig.h the #define USE_PCF8574
  - In the INFO Serial LOG you should see if the board is started
   00:00:00 RSLT: pcf8574 2 boards
   00:00:00 RSLT: Final max devices: 
   if not, use Command I2CSCAN. Board with Address 0x38 should be there. If not wire is wrong
   - Configure your relays in: CONFIGURATION -> CONFIGURE I2C/PCF8574 
  
## 4.1.3a
- Added support for 4 channel A/D converter ADS1115
- Changes MQTT Heap and WEBSERVER HEAP from kByte to Byte

## Sonoff-Tasmota
Provide ESP8266 based Sonoff by [iTead Studio](https://www.itead.cc/) and ElectroDragon IoT Relay with Serial, Web and MQTT control allowing 'Over the Air' or OTA firmware updates using Arduino IDE.

Current version is **4.1.3** - See [sonoff/_releasenotes.ino](https://github.com/arendst/Sonoff-Tasmota/blob/master/sonoff/_releasenotes.ino) for change information.

- This version provides all (Sonoff) modules in one file and starts up with Sonoff Basic.
- Once uploaded select module using the configuration webpage or the commands ```Modules``` and ```Module```.
- After reboot select config menu again or use commands ```GPIOs``` and ```GPIO``` to change GPIO with desired sensor.

<img src="https://github.com/arendst/arendst.github.io/blob/master/media/sonoffbasic.jpg" width="250" align="right" />

See [Wiki](https://github.com/arendst/Sonoff-Tasmota/wiki) for more information.<br />
See [Community](https://groups.google.com/d/forum/sonoffusers) for forum and more user experience.

The following devices are supported:
- [iTead Sonoff Basic](http://sonoff.itead.cc/en/products/sonoff/sonoff-basic)
- [iTead Sonoff RF](http://sonoff.itead.cc/en/products/sonoff/sonoff-rf)
- [iTead Sonoff SV](https://www.itead.cc/sonoff-sv.html)<img src="https://github.com/arendst/arendst.github.io/blob/master/media/sonoff_th.jpg" width="250" align="right" />
- [iTead Sonoff TH10/TH16 with temperature sensor](http://sonoff.itead.cc/en/products/sonoff/sonoff-th)
- [iTead Sonoff Dual](http://sonoff.itead.cc/en/products/sonoff/sonoff-dual)
- [iTead Sonoff Pow](http://sonoff.itead.cc/en/products/sonoff/sonoff-pow)
- [iTead Sonoff 4CH](http://sonoff.itead.cc/en/products/sonoff/sonoff-4ch)
- [iTead S20 Smart Socket](http://sonoff.itead.cc/en/products/residential/s20-socket)
- [iTead Slampher](http://sonoff.itead.cc/en/products/residential/slampher-rf)
- [iTead Sonoff Touch](http://sonoff.itead.cc/en/products/residential/sonoff-touch)
- [iTead Sonoff SC](http://sonoff.itead.cc/en/products/residential/sonoff-sc)
- [iTead Sonoff Led](http://sonoff.itead.cc/en/products/appliances/sonoff-led)
- [iTead Sonoff Dev](https://www.itead.cc/sonoff-dev.html)
- [iTead 1 Channel Switch 5V / 12V](https://www.itead.cc/smart-home/inching-self-locking-wifi-wireless-switch.html)
- [iTead Motor Clockwise/Anticlockwise](https://www.itead.cc/smart-home/motor-reversing-wifi-wireless-switch.html)
- [Electrodragon IoT Relay Board](http://www.electrodragon.com/product/wifi-iot-relay-board-based-esp8266/)

<img src="https://github.com/arendst/arendst.github.io/blob/master/media/sonofftoucheu.jpg" height="280" align="left" /> 
<img src="https://github.com/arendst/arendst.github.io/blob/master/media/sonoff4ch.jpg" height="250" align="right" /> 
