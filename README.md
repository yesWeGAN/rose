

# ROSe Bot 
Converting Elegoo Smart Robot Car v4.0 (with camera) into a ROS2 agent with vision-based functionality.



### milestones
#### 21.02.24
Got a working camera webserver AND working publisher node at the same time!
Wrong pinning config caused the cam init failures. 


#### 14.02.24
Backed myself into a corner by updating Ubuntu 20.04 -> 22.04: <br>
rosserial won't work with ROS2, ROS1 has no distro on 22.04 <br>
proceeding with microROS, but it's too big for my Arduino Uno<br>

Next steps:
- use Espressif ESP32 WROVER with microROS
- try to establish a serial connection from ESP32 to Arduino and publish move control there (RXD2 TXD2)
https://forum.arduino.cc/t/sending-serial-info-from-esp32-to-arduino-on-elegoo-kit/1196616/4s

#### 21.01.24
sudo dmesg
	revealed the serial port /dev/ttyUSB0
ls -l /dev/ttyUSB*
	revealed that only dialout group can rw the serial port
sudo adduser frank dialout
	add user frank to dialout group, which has access to ttyUSB0
	
YAY! Uploading sketch works via VSCode

ESP32-WROVER-KIT:
had to adapt udev rules in order for platformio to recognize USB device. Re-login and physical unplug also required!
https://docs.platformio.org/en/latest/core/installation/udev-rules.html#platformio-udev-rules


