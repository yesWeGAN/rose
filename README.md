

# ROSe Bot 
Converting Elegoo Smart Robot Car v4.0 (with camera) into a ROS2 agent with vision-based functionality.



### milestones

#### 14.02.24
Backed myself into a corner by updating Ubuntu 20.04 -> 22.04: 
rosserial won't work with ROS2, ROS1 has no distro on 20.04
proceeding with microROS, but it's too big for my Arduino Uno

Next steps:
- use Espressif ESP32 WROVER with microROS
- try to establish a serial connection from ESP32 to Arduino and publish move control there (RXD2 TXD2)

#### 21.01.24
sudo dmesg
	revealed the serial port /dev/ttyUSB0
ls -l /dev/ttyUSB*
	revealed that only dialout group can rw the serial port
sudo adduser frank dialout
	add user frank to dialout group, which has access to ttyUSB0
	
YAY! Uploading sketch works via VSCode


