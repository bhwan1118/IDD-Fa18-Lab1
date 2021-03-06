# IDD-Fa18-Lab1: Blink!

**A lab report by Benjamin Hwang**

## Part A. Set Up a Breadboard

![My image](https://github.com/bhwan1118/IDD-Fa18-Lab1/blob/master/Breadboard%20Setup.jpg)

## Part B. Manually Blink a LED

**a. What color stripes are on a 100 Ohm resistor?**
 
 From left to right: Brown, Black, Brown, Gold (this tolerance can be other colors as well)
 
**b. What do you have to do to light your LED?**

You must press the switch in order to light the LED.

## Part C. Blink a LED using Arduino

### 1. Blink the on-board LED

**a. What line(s) of code do you need to change to make the LED blink (like, at all)?**

You need to add lines : pinMode(LED_BUILTIN, OUTPUT); under setup() and then lines : digitalWrite(LED_BUILTIN, HIGH) and digitalWrite(LED_BUILTIN, LOW) to switch the LED on and off along with a set delay() to specify how light should stay on and off.
See code snippet here: [Lab 1 Code](https://github.com/bhwan1118/IDD-Fa18-Lab1/blob/master/CustomBlink.ino)

**b. What line(s) of code do you need to change to change the rate of blinking?**

You need to change the delay(1000) lines to vary the rate of blinking. Lowering the value in the delay() line after digitalWrite(LED_BUILTIN, LOW) will decrease the time which the LED stays off and reducing the other delay value after digitalWrite(LED_BUILTIN, HIGH) will decrease the time at which the LED stays on which in effect increases the rate at which the LED blinks.   

**c. What circuit element would you want to add to protect the board and external LED?**

I would add some type of resistor to reduce the amount of current that is flowing through the circuit.
 
**d. At what delay can you no longer *perceive* the LED blinking? How can you prove to yourself that it is, in fact, still blinking?**

If I set the delay() after digitalWrite(LED_BUILTIN, LOW) to around delay(1) (1 milisecond) I can no longer perecieve the LED blinking it just looks like it is continuously on. One way I can think of is by connecting some kind of voltmeter that can quickly record voltage readings. You then should hypothetically see the voltage reading drop and spike which would indicate the LED was blinking. Another thought is to get a camera that has a fast shutterspeed so that you could actually see the blink.

**e. Modify the code to make your LED blink your way. Save your new blink code to your lab 1 repository, with a link on the README.md.**

Code : [Custom Blink](https://github.com/bhwan1118/IDD-Fa18-Lab1/blob/master/CustomBlink.ino)

### 2. Blink your LED

**Make a video of your LED blinking, and add it to your lab submission.**

[YouTube Demo](https://youtu.be/2N3m1axUkBE)

## Part D. Manually fade an LED

**a. Are you able to get the LED to glow the whole turning range of the potentiometer? Why or why not?**

Yes I am able to get the LED to glow the whole range. When you turn the potentiometer you are varying the resistance between 0 Ohms to 10k Ohms. Since this is a circuit with a resistor in series, the total resistance of the circuit is simply the sum of the potentiometer value and the 220 Ohm resistor that is listed. Since this is the case the max brightness of the LED will occur when the potentiometer is at 0 (most current flowing through the circuit) and be the dimmest when the potentiometer is at its max value. At the potentiometer's max value there is still enough current to provide the needed voltage to power the LED thus you can utilize the whole range of the potentiometer.

## Part E. Fade an LED using Arduino

**a. What do you have to modify to make the code control the circuit you've built on your breadboard?**

In this case the only parameter that needed changing was the variable led needed to be set to 11 to correspond to the value of the pin powering the LED in this circuit.

**b. What is analogWrite()? How is that different than digitalWrite()?**

Upon observation, analogWrite() takes an integer argument for specifying a value to write to a specified pin, whereas digitalWrite() can only take the binary values: High/Low. According to Arduino reference online, this is accomplished by a pulse width modulation wave actually uses an analog signal (as specified by code) to vary the voltage being supplied to a pin.

## Part F. FRANKENLIGHT!!!

### 1. Take apart your electronic device, and draw a schematic of what is inside. 

![My Image](https://github.com/bhwan1118/IDD-Fa18-Lab1/blob/master/Schematic%20Drawing.jpg)

**a. Is there computation in your device? Where is it? What do you think is happening inside the "computer?"**

Yes. it is towards the top of the PCB. It's doing calculations (since this is a calculator) and I think it is also sending signals for what the screen should be displaying. 

**b. Are there sensors on your device? How do they work? How is the sensed information conveyed to other portions of the device?**

Yes. There are pressure sensors on the front of the PCB. Each sensor corresponds to a button on the calculator and everytime it is pressed that information must be communicated as an electrical signal to the computer to be processed.

**c. How is the device powered? Is there any transformation or regulation of the power? How is that done? What voltages are used throughout the system?**

This appears to be accomplished in a few different ways. There is a solar panel, a big capacitor, and a battery. Power probably flows in and out of these components and is also regulated by resistors and diodes that are on the board.

**d. Is information stored in your device? Where? How?**

### 2. Using your schematic, figure out where a good point would be to hijack your device and implant an LED.

Unfortunately my device no longer capable of supplying power to itself. That being said, I used the power from the microcontroller and then connected wires from my circuit to the PCB board so that power could flow through PCB board components and then back to ground in my breadboard. This allows my LED to light up when in touch with the components in the PCB. It also supplied enough power to make the calculator functional again which was an interesting bi-product. 

### 3. Build your light!

[Frankenlight Part 1](https://youtu.be/VSvGoaRdlk8)
[Frankenlight Part 2](https://youtu.be/wt5-G86fvRk)

