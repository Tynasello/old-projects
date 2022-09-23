# Arduino Robot Car

![ARProject2 e1d380ff](https://user-images.githubusercontent.com/63558019/184507798-5051edc2-8b3d-4c65-9997-5ae23dcc63ab.jpg)


The purpose of this project was to create a fully functional robot using an Arduino Uno microcontroller. The robot performs certain maneuvers based on input from a Bluetooth terminal application. The robot has an optional autonomous mode which when activated, will cause the robot to drive forward, redirecting its route only when the ultrasonic sensor detects an object within 10 cm.

### Functionality
The Arduino is responsible for commanding all parts of the robot. The robot's HC-SR04 ultrasonic sensor and HC-08 Bluetooth module are connected to the Arduino's analog and digital pins respectively. The Arduino is powered via a USB-connected power bank. The L293D motor controller shield plugs into the top of the Arudino and operates the motors on the chassis.

All actions performed by the robot are due to input from a Bluetooth terminal application. When specific characters are sent via Bluetooth to the robot's HC-08 module, corresponding actions are performed.

![ARProject1 b85779df](https://user-images.githubusercontent.com/63558019/184507814-91daa220-5dfc-4233-a3fa-8f2aeb5244f5.png)


### Coding
The program to control the robot was written in the Arduino IDE using the programming language C++. The AFMotor.h library provided simultaneous speed and directional motor control. The NewPing.h library delivered ultrasonic sensor functionality. Lastly, the SoftwareSerial.h library was leveraged to allow serial communication between a Bluetooth terminal and the Arduino via the HC-08.

### Final Product

https://www.dropbox.com/s/4fgv8d03ylhvlvf/RobotCar.mp4?dl=0