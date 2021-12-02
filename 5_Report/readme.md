FINGER PRINT LOCKER SYSTEM - By Kushla Devi

##### **Requirements**
 **# :**

This project is to build a Finger Print Based Bank Locker Security system where we can secure the Locker Storage using this system and make if safer than before. The fingerprint based bank locker system is an enhancement to the traditional bank locker system that uses keys.

## **Identify Features:**

- Finger Print Sensor
- LCD Screen Display
- Motorized Operation

## State of art/Research:

Fingerprint based bank locker system is here to solve all these issues. The fingerprinted authenticated bank locker system is safe as well as easy to use and maintain. No key handling no need to worry about key getting lost. The system uses fingerprint sensing to read fingerprints and first store registered fingerprints against the bank locker record. Now next time a person scans finger the sensor reads it and compares it with past records. Now if match is found with existing prints, it sends the match signal to the microcontroller and the controller displays this data on the LCD display. Also the controller drives the driver motor to open the bank locker door and opens it for authorized customers. The door of locker wont open for unauthorized customers.

**4-W&#39;s and 1-H:**

### **Why:**

### This method of authentication is more reliable and advanced.

###


### **Where:**

### The system are mainly build for lockers but can be installed and used anywhere if the possessions are very valuable/precious.

###


### **Who:**

### It can be used by any person.

###


### **When:**

### It can be used at anytime depending upon the customer&#39;s/user&#39;s preferences.

###


### **How:**

### By putting the finger over the finger print sensor you can open the locker. Without that the locker won&#39;t open.

**SWOT Analysis:**

### **STRENGTH:**

- Simple and easy to operate.
- Inbuilt LCD screen
- Saves time.
- Very secure
- No internet is needed.

### **WEAKNESS:**

- The interface is not as good.

### **OPPORTUNITIES:**

- We can enhance the security methods and introduce some other ways of authentication.

### **THREATS:**

- Not immune to all the security threats and hacking.

#### **HIGH LEVEL REQUIREMENTS**

| **High Level Requirements** | **Description** |
| --- | --- |
| HLR1 | Finger Print Sensor |
| --- | --- |
| HLR2 | Switches |
| HLR3 | Motor |
| HLR4 | Microcontroller |
| HLR5 | Software used |
| HLR6 | Display |

# **LOWLEVEL REQUIREMENTS**

| **Low Level Requirements** | **Description** |
| --- | --- |
| HLR1\_LLR1 | Finger Print module |
| --- | --- |
| HLR2\_LLR1 | Push Button |
| HLR4\_LLR1 | ATMEGA 328 |
| HLR5\_LLR1 | Code Blocks with AVR GCC compiler |
| HLR6\_LLR1 | SimulIDE LCD and LED |

##### **DESIGN**

-
##### Fingerprint locker system is design to take input and the verify that input to take further actions.
- The main aim is to verify authentication and use the motor to open the locker.
- If the authentication fails, the motor does not open the locker.

##### **DIFFERENT DESIGN LEVEL**

-
##### Behavioral Design
- Structural Design

##### **BEHAVIOURAL DESIGN:**

![](RackMultipart20211202-4-1uq90ol_html_f01cce10829a7f84.png)

##### **BLOCK/STRUCTURAL DESIGN:**

![](RackMultipart20211202-4-1uq90ol_html_188b163d38a2738.png)

**SOURCE CODE**

We need to download some libraries. First of all we need the Adafruit Fingerprint library, the Adafruit GFX library and the Sumotoy&#39;s library for the display.

[https://github.com/adafruit/Adafruit-Fingerprint-Sensor-Library](https://github.com/adafruit/Adafruit-Fingerprint-Sensor-Library)

[https://github.com/adafruit/Adafruit-GFX-Library](https://github.com/adafruit/Adafruit-GFX-Library)

[https://github.com/sumotoy/TFT\_ILI9163C](https://github.com/sumotoy/TFT_ILI9163C)

#include \&lt;SPI.h\&gt;

#include \&lt;Adafruit\_GFX.h\&gt;

#include \&lt;TFT\_ILI9163C.h\&gt;

#include \&lt;Adafruit\_Fingerprint.h\&gt;

#include \&lt;SoftwareSerial.h\&gt;

#include \&lt;avr/pgmspace.h\&gt;

**void** setup( **void** )

{

startFingerprintSensor();

display.begin();

displayLockScreen();}

**void** loop(){

fingerprintID = getFingerprintID();

delay(50);

**if** (fingerprintID ==1)

{

display.drawBitmap(30,35,icon,60,60,GREEN);

delay(2000);

displayUnlockedScreen();

displayIoanna();

delay(5000);

display.fillScreen(BLACK);

displayLockScreen();

}

**if** (fingerprintID ==2)

{

display.drawBitmap(30,35,icon,60,60,GREEN);

delay(2000);

displayUnlockedScreen();

displayNick();

delay(5000);

display.fillScreen(BLACK);

displayLockScreen();

}}

**IMAGES**

![](RackMultipart20211202-4-1uq90ol_html_93e03b3321420b70.png) ![](RackMultipart20211202-4-1uq90ol_html_39738e25677c137e.png) ![](RackMultipart20211202-4-1uq90ol_html_402e0e0fbf96e180.png)
