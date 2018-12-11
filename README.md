# Chirp! Water sensor

Chirp! water sensor is also known as plant watering alarm. This sensor helps to extend the life of plant by reminding person to water it.  This sensor is placed near a plant and it emits a tiny chirp when the soil is dry. It uses capacitive humidity sensing as opposed to resistive humidity sensing. This alarm sensor not only beeps at lower level but also sense light using light sensor present in it. The light sensor helps chirp to not let alarm to make much noise when it's dark. This sensor is not that difficult to work with if you know it's functionality properly and it's soul purpose is to remind person to water plant which helps in extending it's life.

# Component requirements

##### -> Raspberry pi3 B+
##### -> Chirp! Water Sensor
##### -> Male to female jumper wires and breadboard to test temporary circuit connections
##### -> PCB board with final circuit printed on it with correct address.
##### -> Socket header
##### -> Enclosure (case) to hold circuit together.


# Overall Budget

![capture](https://user-images.githubusercontent.com/43180510/49830888-74056b00-fd60-11e8-93dd-53d7ad498b5c.PNG)

I was able to arrange soil from nursery and socket header from prototype lab. Their can be additional charges for that too if you want to buy that youself. Other than that overall budget will be same as shown in table.

# Time Commitment

This schedule is made before we started working on our project (to keep us on track).

![capture2](https://user-images.githubusercontent.com/43180510/49831279-7caa7100-fd61-11e8-84f4-4baeed8bc161.PNG)

The only thing you need to keep in mind is that you need to press restart button twice to bring sensor in active mode and to get readings.

# Mechanical Assembly

## Setup raspberry pi
If you're installing os  first time on raspberry pi and don't know how to do it, follow the below steps:

### Step1. Download Raspbian
It can easily take more than half an hour to download the software.Download Noobs from https://www.raspberrypi.org/downloads/

### Step2. Download SDcard Formatter
Download SDcard formatter from https://www.sdcard.org/downloads/formatter_4/eula_windows/

### Step3. Unzip the raspbian file
The Raspbian disc image is compressed, so you’ll need to unzip it. The file uses the ZIP64 format, so depending on how current your built-in utilities are, you need to use certain programs to unzip it.

### Step4. Write the disc image to your microSD card
Select the drive of your SD card in the ‘Device’ dropdown.

### Step5. Put the microSD card in your Pi and boot up
Select ‘Write’ and wait for the process to finish which may take around 20 minutes to complete

# Hardware Setup
Starting with connections you have to make sure your sensor is at the right address. Connections you need to make using male to female jumper wires are:

##### -> Connect SDA (pin #4) from sensor to SDA on pi (pin #2)
##### -> Connect SCL (pin #3) from sensor to SCL on pi (pin #3)
##### -> Connect GND (pin #6) from sensor to ground pin 5 on raspberry pi.
##### -> Connect VCC (PIN #2) from sensor to 3.3V first pin of raspberry pi.

You don't need to make any connection of sensor's MISO and RESET pins. We are not using them. We are using two resistors to make our sensor work properly with I2C.


Address of chirp! water sensor is 00x20. Below are the screenshots of address connection and it's output.

![capture3](https://user-images.githubusercontent.com/43180510/49832216-09eec500-fd64-11e8-8926-fbe4158946cc.PNG)

To check if your connections are correct and you are getting correct address, than open terminal on pi and type command: 
#### i2cdetect -y 1

You will get the following output:

![capture4](https://user-images.githubusercontent.com/43180510/49832232-107d3c80-fd64-11e8-952c-4b40d1df1ea6.PNG)

# PCB and Soldering
Once you know how to do all the connections, you need to carefully design your PCB using Fritzing software. PCB you made is a permanent board (containing your circuit conections you made before) which you are going to use in your project.

![capture5](https://user-images.githubusercontent.com/43180510/49833015-44596180-fd66-11e8-984f-3fee248cdc28.PNG

The wires that are yellow in colour are on the top side of the board and orange ones are at the bottom. It is important not to cross two wires on the same side of board. Next step is to get your PCB board made once you have got your PCB ready carefully solder socket headers to the PCB you have to very carefull. Safety is the first priority so it is important to know what are you working with. If you haven't done soldering before you should get help from someone with experience or from youtube videos. For above design I have this PCB should look like this:

![capture6](https://user-images.githubusercontent.com/43180510/49833175-b9c53200-fd66-11e8-841a-4eab15cc589d.PNG)

After that you can just attached your sensor and raspberry pi to PCB. Make sure all the wires are connected and your sensor is at the correct address.

![capture7](https://user-images.githubusercontent.com/43180510/49833218-d6fa0080-fd66-11e8-8a28-e1ab9fa1e660.PNG)

Now you might be curious to know why I am still using jumper wires after all the connections. Here is the answer. I have to put half of my sensor into plant (or soil) which is not possible to do if I connect my sensor to the PCB board. The only solution to this problem is to use jumper wires (male to female).


# Sensor Readings

At this point you should have your raspberry pi and sensor ready to use to read data. Here i am ruuning this python code over here.

![capture10](https://user-images.githubusercontent.com/43180510/49833747-6e138800-fd68-11e8-9247-2768e7c623cb.PNG)
![capture12](https://user-images.githubusercontent.com/43180510/49833802-9e5b2680-fd68-11e8-989f-826c043cf39b.PNG)

My sensor not only takes misture readings, but also light and temperature readings. Above is the code I am using to obtain data. 
#### *The only thing you need to keep in mind is that you need to press restart button twice to bring sensor in active mode and to get readings.

# Data display
The output you should be obtaining are:

![capture13](https://user-images.githubusercontent.com/43180510/49833891-eb3efd00-fd68-11e8-974f-557d685912db.PNG)

Try to obtain different readings for moisture and brightness by putting more water or covering light sensor.

# Enclosure

Now you are having your chirp! water sensor working. At this point of time, you may want to build a case to protect your pi and prevent it from damage. You need to use Corel Draw software for that. To build a case that is perfect for your pi first thing you need to do is to get all the measurements for example Height, Width, Length. If you don't know how to use this software you can visit to the following link:
https://www.coreldraw.com/en/pages/tutorials/coreldraw/

Below is the picture of my corel file. Hope it will be helpful :)
![capture14](https://user-images.githubusercontent.com/43180510/49834202-d4e57100-fd69-11e8-8cac-b2e7d56b9022.PNG)


After you got your case pieces sperated using laser cut, you can combine them to get perfect case:

![capture15](https://user-images.githubusercontent.com/43180510/49834277-03634c00-fd6a-11e8-95a9-37700ef21555.PNG)


You can use cable harnass instead of jumper wires. Laser cutting will be costly, so you can use injection moulding as it's alternative.

