# IDD-Fa18-Lab1: Blink!

**A lab report by Benjamin Hwang**

**Fork** this repository to get a template for Lab 1 for *Developing and Designing Interactive Devices* at Cornell Tech, Fall 2018. You should modify this `README.md` file to delete this paragraph and update below. As the lab asks:

> Include your responses to the bold questions on your own fork of the lab activities. Include snippets of code that explain what you did. Deliverables are due next Tuesday. Post your lab reports as `README.md` pages on your GitHub, and post a link to that on your main class hub page.

We've copied the questions from the lab here. Answer them below!

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
See code snippet here: ![Lab 1 Code](google.com)

**b. What line(s) of code do you need to change to change the rate of blinking?**

You need to change the delay(1000) lines to vary the rate of blinking. Lowering the value in the delay() line after digitalWrite(LED_BUILTIN, LOW) will decrease the time which the LED stays off and reducing the other delay value after digitalWrite(LED_BUILTIN, HIGH) will decrease the time at which the LED stays on which in effect increases the rate at which the LED blinks.   

**c. What circuit element would you want to add to protect the board and external LED?**

I would add some type of resistor to reduce the amount of current that is flowing through the circuit.
 
**d. At what delay can you no longer *perceive* the LED blinking? How can you prove to yourself that it is, in fact, still blinking?**

If I set the delay() after digitalWrite(LED_BUILTIN, LOW) to around delay(1) (1 milisecond) I can no longer perecieve the LED blinking it just looks like it is continuously on. One way I can think of is by connecting some kind of voltmeter that can quickly record voltage readings. You then should hypothetically see the voltage reading drop and spike which would indicate the LED was blinking. Another thought is to get a camera that has a fast shutterspeed so that you could actually see the blink.

**e. Modify the code to make your LED blink your way. Save your new blink code to your lab 1 repository, with a link on the README.md.**



### 2. Blink your LED

**Make a video of your LED blinking, and add it to your lab submission.**

[link to your video here; feel free to upload to youtube and just paste in a link here]


## Part D. Manually fade an LED

**a. Are you able to get the LED to glow the whole turning range of the potentiometer? Why or why not?**


## Part E. Fade an LED using Arduino

**a. What do you have to modify to make the code control the circuit you've built on your breadboard?**

**b. What is analogWrite()? How is that different than digitalWrite()?**


## Part F. FRANKENLIGHT!!!

### 1. Take apart your electronic device, and draw a schematic of what is inside. 

**a. Is there computation in your device? Where is it? What do you think is happening inside the "computer?"**

**b. Are there sensors on your device? How do they work? How is the sensed information conveyed to other portions of the device?**

**c. How is the device powered? Is there any transformation or regulation of the power? How is that done? What voltages are used throughout the system?**

**d. Is information stored in your device? Where? How?**

### 2. Using your schematic, figure out where a good point would be to hijack your device and implant an LED.

**Describe what you did here.**

### 3. Build your light!

**Make a video showing off your Frankenlight.**

**Include any schematics or photos in your lab write-up.**
