3-Axis Accelerometer- By Arman Velani

<h1 align="center">MMA8451(Triple Axis Accelerometer)</h1>

<p align="center">
<a href="https://github.com/ArmanVelani/3-AxisAccelerometer/archive/master.zip">Download as .zip</a>
</p>
<div align="center">
<h2 align="center">System Diagram</h2>
<img src="https://user-images.githubusercontent.com/43188450/48367169-deea5600-e67d-11e8-9f60-53604ff9a58f.png" width="80%" height="80%"  alt="image not found">
</div>

## About the MMA8451 ##

The MMA8451 is a low-cost but high-precision digital accelerometer that uses repeated-start I2C mode, with adjustable data rata and 'range' (+/-2/4/8).In this project it is used to measure the accel readings using raspberry pi 3.
More information on the MMA8451 can be found in the [datasheet](http://www.adafruit.com/datasheets/MMA8451Q-1.pdf)

# Initial Preparation
Before starting with any project create your Budget about the project. Once you have your Budget create a Schedule for your project. My project total Budget was $384 and the total time to complete the project was 4 months. The budget may vary as the prices of the parts changes. The schedule may also vary depending on the personal Schedule. My [Budget](https://github.com/ArmanVelani/3-AxisAccelerometer/blob/master/Budget.xlsx), [Schedule](https://github.com/ArmanVelani/3-AxisAccelerometer/raw/master/Schedule.mpp) and [Bills of the material](https://github.com/ArmanVelani/3-AxisAccelerometer/blob/master/Bills.md) are as follows.

# Parts Requirement
1. [Raspberry Pi 3 Ultimate Starter kit-32 GB Edition](https://www.adafruit.com/product/3058).   $141.17
2. [Adafruit Triple-Axis Accelerometer - 2/4/8g @ 14 bit - MMA8451](https://www.amazon.ca/gp/product/B00SK8LS4Q/ref=oh_aui_detailpage_o01_s00?ie=UTF8&psc=1)   $30.5
3. [Anker Unibody Aluminium USB 3.0 to Rj45 Gigabit Ethernet Adapter Supporting 10/100/1000 Mbps Ethernet [RTL8153 Chipset]](https://www.amazon.ca/Anker-Unibody-Aluminum-Ethernet-Supporting/dp/B00PC0H9IE/ref=sr_1_1?s=electronics&ie=UTF8&qid=1544565134&sr=1-1&keywords=Anker+Unibody+Aluminium+USB+3.0+to+Rj45+Gigabit+Ethernet+Adapter+Supporting+10%2F100%2F1000+Mbps+Ethernet)  $31.53
4. Parts kit [tool box] $135.60
5. headers [[1xGPIO female header](https://www.adafruit.com/product/2222), [1x8 female header](https://www.creatroninc.com/product/stackable-header-set-for-arduino/?search_query=8+pin+stackable+header&results=48), [Stackable Headers](https://www.creatroninc.com/product/stackable-header-for-raspberry-pi/)] 
6. [Raspberry Pi 3 and sensor case].(https://github.com/ArmanVelani/3-AxisAccelerometer/raw/master/Pi2Casestack.cdr)
7. [LED, soldering station, Twizers](https://www.amazon.ca/Soldering-Adjustable-Temperature-Controlled-Welding/dp/B06Y5ZSCWQ/ref=sr_1_5?ie=UTF8&qid=1544565219&sr=8-5&keywords=soldering+led) other [cables](https://www.amazon.ca/Copper-Jumper-Single-Conductor-AWG30/dp/B00HR6JX80/ref=sr_1_7?ie=UTF8&qid=1544565319&sr=8-7&keywords=jumper+cables+pcb)
8. [wireless keyboard and mouse with usb reciver](https://www.amazon.ca/Wireless-Keyboard-Touchpad-Trackpad-Raspberry/dp/B01N6O1TS4/ref=sr_1_fkmr2_1?ie=UTF8&qid=1544565366&sr=8-1-fkmr2&keywords=usb+mouse+with+trackpad+logitech).    $45.20
9. 4xM2.5 bolts, 4xM2.5 nut.
10.One HDMI monitor
11. One HDMI cable.

# Setup Raspberry Pi
This section explains how to setup the whole things to test your MMA8451 device on a Raspberry Pi. Once you have all The parts with you start with your raspberry Pi. Make Sure you do not power on the Raspbery Pi, Monitor or any other Components before finishing the setup. Connect a wireless keyboard/Mouse to your Raspberry Pi. Also attach one end of HDMI cable to your Raspberry Pi and other end to the Monitor. Once connected poweron the raspberry pi and Complete the Setup. For Help on Setting up raspberry Pi 3 visit this [Youtube Video.](https://www.youtube.com/watch?v=xBlxuf_LSCM).

# Connection
Now you need to Power off your raspberry Pi and disconnect the Power Source. Connect you MMMA8451 usingh some jumper cables as shown in the image Below.<br>
<img src="https://user-images.githubusercontent.com/43188450/48366908-35a36000-e67d-11e8-9476-107ec0f8258f.jpeg" width="35%">
<ul><li>raspberry Ground- MMA8451 Ground</li>
<li>raspberry 3.3V- MMA8451 3.3V</li>
<li>raspberry SCA- MMA8451 SCA</li>
<li>raspberry SCL- MMA8451 SCL</li></ul>
Once you have your Connections connect Power to raspberry pi and power it on.
User command I2C Detect to check if the Sensor is connected properly.

# Designing and Printing a PCB.
Now you have your connections ready what you need is a PCB. you can [Download](https://github.com/ArmanVelani/3-AxisAccelerometer/raw/master/MMA8451.fzz) my PCB that I created using the Fritzing Software. or you can design your own. Here is a tutorial on [fritzing](https://www.youtube.com/watch?v=M4CvUSkP9hw).
<center>
<img src="https://user-images.githubusercontent.com/43188450/48366901-30deac00-e67d-11e8-860c-0fb92a65a9b9.jpeg" width="50%">
<center>
Now you Export your file for production as Gerber file. You can go to any local Company who Prints PCB.
When you have your PCB use the stackable header for the RaspBerry and the Other Header soldered on the PCB. For tutorial on how to solder headers properly visit [here](https://learn.adafruit.com/adafruit-mma8451-accelerometer-breakout/assembly).

This is how it should look when soldering is completed.
<center>
<img src="https://user-images.githubusercontent.com/43188450/48862001-01bdee00-ed93-11e8-898b-70c879b291d1.jpeg" width="35%">
<center>

# Code
Now you have you PCB ready but it is not still reading the code in order to read from the sensor you will need a python code.
[Get the code](https://github.com/ArmanVelani/3-AxisAccelerometer/blob/master/PythonCode.txt). compile the code and run it using 'sudo python3 <filename>'
this is the [video](https://github.com/ArmanVelani/3-AxisAccelerometer/raw/master/WhatsApp%20Video%202018-11-13%20at%2010.57.24%20PM.mp4) of how the sensor should work when the code is running sucessfully.
this is how the [code output](https://user-images.githubusercontent.com/43188450/48862483-81988800-ed94-11e8-902c-ec6e4a4453eb.jpeg) and [PCB](https://user-images.githubusercontent.com/43188450/48862531-a260dd80-ed94-11e8-9e08-a28f0783966a.jpeg) looks.
  
# case
To create the case just download the [coralDraw](https://github.com/ArmanVelani/3-AxisAccelerometer/raw/master/Pi2Casestack.cdr) file of my case and send it for lasercutting. when your laser cut case is ready it should be like the image below. you can use it to stack multile sensors on the same raspberry pi.
<img src="https://user-images.githubusercontent.com/43188450/49106925-70e38880-f252-11e8-94d2-0dfc12e6c991.jpeg" width ="50%">

# testing 
If you are creating an individual project you can follow the instrucions above and test it at each and every step before proceding further. for example test out thr breadboard then test out the pcb then test out the code then check ase measuremenet and test out the case and so on.

If you are considering it as a mass prodution project i would suggest to have some necessary changes like create a printed multilayer circuit board which takes less space then the design above. Also another thing to consider for the PCB is to make it water resistant. the next item to look for would be the casing as a stackable case idea is not so good for a mass production because its delicate. instead you can go for plastic 3D printed cases and not aclervlic laser cutted cases.




