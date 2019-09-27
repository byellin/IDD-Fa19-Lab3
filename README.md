# Data Logger (and using cool sensors!)

*A lab report by Benjamin Yellin.*

## In The Report

Include your responses to the bold questions on your own fork of [this lab report template](https://github.com/FAR-Lab/IDD-Fa18-Lab2). Include snippets of code that explain what you did. Deliverables are due next Tuesday. Post your lab reports as README.md pages on your GitHub, and post a link to that on your main class hub page.

For this lab, we will be experimenting with a variety of sensors, sending the data to the Arduino serial monitor, writing data to the EEPROM of the Arduino, and then playing the data back.

## Part A.  Writing to the Serial Monitor
 
**a. Based on the readings from the serial monitor, what is the range of the analog values being read?**

The analog values range from 358 to 1023.  
 
**b. How many bits of resolution does the analog to digital converter (ADC) on the Arduino have?**

The ADC on the Arduino has 10 bits of resolution (it goes up to 1023.)

## Part B. RGB LED

**How might you use this with only the parts in your kit? Show us your solution.**

## Part C. Voltage Varying Sensors 
 
### 1. FSR, Flex Sensor, Photo cell, Softpot

**a. What voltage values do you see from your force sensor?**

Minimum value: 305
Maximum value: 1023

**b. What kind of relationship does the voltage have as a function of the force applied? (e.g., linear?)**

Looking at the serial plotter, the relationship is logistic. 

**c. Can you change the LED fading code values so that you get the full range of output voltages from the LED when using your FSR?**

**d. What resistance do you need to have in series to get a reasonable range of voltages from each sensor?**

For the short flex sensor, the range of resistances are between 25 and 100 kilo-ohms. For the photo cell, the range of resistances is between 5 and kilo-ohms when it is bright and 200 kilo-ohms when it is dark. The linear softspot resistor ranges from 10 kilo-ohms and 100,000 kilo-ohms. 

**e. What kind of relationship does the resistance have as a function of stimulus? (e.g., linear?)**

Looking at the serial plotter, the relationship is logistic. 

### 2. Accelerometer
 
**a. Include your accelerometer read-out code in your write-up.**

[Insert screenshot in folder]

## Optional. Graphic Display

**Take a picture of your screen working insert it here!**

![](https://github.com/byellin/IDD-Fa19-Lab3/blob/master/Graphic%20Display.JPG)

## Part D. Logging values to the EEPROM and reading them back
 
### 1. Reading and writing values to the Arduino EEPROM

**a. Does it matter what actions are assigned to which state? Why?**

In order for the Arduino to store the value computed, it needs to clear the memory, then write to the memory, then read the memory. If the memory was read before it was written to, it would always be empty. 

**b. Why is the code here all in the setup() functions and not in the loop() functions?**

We only need to write the value to memory one time, so it does not have to be inside of loop. 

**c. How many byte-sized data samples can you store on the Atmega328?**

You can store 1024 bytes on the Atmega328. 

**d. How would you get analog data from the Arduino analog pins to be byte-sized? How about analog data from the I2C devices?**

If you call analogRead on Arduino analog pins it will return a byte-sized analog reading of the pin. 

**e. Alternately, how would we store the data if it were bigger than a byte? (hint: take a look at the [EEPROMPut](https://www.arduino.cc/en/Reference/EEPROMPut) example)**

To store data larger than one byte, you can use multiple memory addresses to refer to a particular value. 

**Upload your modified code that takes in analog values from your sensors and prints them back out to the Arduino Serial Monitor.**

### 2. Design your logger
 
**a. Insert here a copy of your final state diagram.**

![](https://github.com/byellin/IDD-Fa19-Lab3/blob/master/IMG_6948.JPG)

### 3. Create your data logger!
 
**a. Record and upload a short demo video of your logger in action.**

https://github.com/byellin/Developing-and-Designing-Interactive-Devices/blob/2019Fall/IMG_6947.MOV
