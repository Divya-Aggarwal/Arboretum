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

You don't need to make any connection of sensor's MISO and RESET pins. We are not using them.


Address of chirp! water sensor is 00x20. Below are the screenshots of address connection and it's output.

![capture3](https://user-images.githubusercontent.com/43180510/49832216-09eec500-fd64-11e8-8926-fbe4158946cc.PNG)

To check if your connections are correct and you are getting correct address, than open terminal on pi and type command: 
#### i2cdetect -y 1

You will get the following output:

![capture4](https://user-images.githubusercontent.com/43180510/49832232-107d3c80-fd64-11e8-952c-4b40d1df1ea6.PNG)

