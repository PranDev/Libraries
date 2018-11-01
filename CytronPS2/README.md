# Introduction

This is a slight modification of the Cytron_PS2Shield library, as this library will be used for
PS2 Controllers.
Check the link for the [PS2 Controller](https://github.com/RoboManipal-9-0/Libraries/edit/akshatha-PS2-lib/PS2Controller)

## User's Guide
## Conventions
Please refer to the image below for the conventions followed in the library.
![Joystick conventions](../DATA/Images/Joystick.png)
The image is taken from top view.

### Downloading the library
It is suggested that you download the entire repository and then select this folder.
You can simply open a terminal (or gitbash on windows), go to the folder where you want to save this repository and type the following command.
```
git clone https://github.com/RoboManipal-9-0/Libraries.git
```
## Using the library with Arduino
Move this folder into the arduino libraries folder on your PC.

## Examples
After moving the library to the correct location, you can check the following examples.

They are to give you a basic introduction to the CytronPS2 library.

### Example 1
This example demonstartes how to read button presses on a joystick. The LED on the main board lights up if the 'Select' button is pressed. ( You modify it to do so with any button of your choice ).
![PS2ReadButton](../DATA/Images/PS2ReadButton.jpg)

### Example 2
This example demonstartes how to read the analog values on a joystick. The analog values read by the left joystick are displayed on the serial monitor. ( You modify it to do so with the Y coordinate as well as the X and Y coordinates of the right joystick ).
![PS2TestAnalog](../DATA/Images/PS2TestAnalog.jpg)

Note: 
- Set the baudrate of the PS2 Serial that matches with the jumper setting on the PS2 Shield. 
- Do not call the Initialize() function if you are using it with Hardware Serial.

# Developers Guide

## Modifications made to Cytron_PS2Shield:

#### CytronPS2.cpp
- Eliminating the parameterised constructor.
- Added a function **<font color="#CD00FF">void</font> <font color="#5052FF">Initialize</font>(<font color="#FF00FF">uint8_t</font> rxpin, <font color="#FF00FF">uint8_t</font> txpin)** :
 Used to initialize the software serial pins. This has been done in order to enable the custom PS2 Controller classes to initialise it.
  
## Making your own custom PS2 Controller
You must create an object of the CytronPS2 class and then create your own functions (that call the CytronPS2 member functions) to map the joystick values
as required and to assign the desired functions to the buttons on the PS2.

#### Examples 
We have already created an example library. 
Click here for the [PS2 Controller](https://github.com/RoboManipal-9-0/Libraries/edit/akshatha-PS2-lib/PS2Controller)
It reads various buttons to start and stop the bot motion, and also assign modes. The analog values from the joystick are used to take angle and speed inputs.
This library maps the values of X and Y from -128 to 127 and calculates the angle of bot motion in radians.

#### Original Cytron_PS2Shield
 [Cytron-PS2-Shield](https://github.com/CytronTechnologies/Cytron_PS2Shield)

