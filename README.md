<div id="readme" class="Box-body readme blob js-code-block-container">
 <article class="markdown-body entry-content p-3 p-md-6" itemprop="This needs to locked down and 'never' changed"><p><a href="https://www.microchip.com" rel="nofollow"><img src="images/MicrochipLogo.png" alt="MCHP" style="max-width:40%;"></a></p>

# PIC18F47Q10 GPIO Interrupt 

## Objective

The PIC18F47Q10 provides multiple PORT modules.

In this example, the interrupt is configured to be triggered on the falling edge of the input signal (the value is changed from logic ‘1’ to logic ‘0’), in order to generate the interrupt when the button is pressed. The interrupt routine consists in toggling the output pin value, causing the LED to turn on and off.

For this example, the RA0 pin is configured as input with IOC enabled on falling edge and connected to a button, and the RE0 pin is configured as output and connected to an LED.

## Related Documentation

- [TB3284: Getting Started with GPIO on PIC18](https://www.microchip.com/wwwappnotes/appnotes.aspx?appnote=en1003275)
- [PIC18-Q10 Product Family Page](https://www.microchip.com/design-centers/8-bit/pic-mcus/device-selection/pic18f-q10-product-family)
- [PIC18F47Q10 Data Sheet](http://ww1.microchip.com/downloads/en/DeviceDoc/40002043D.pdf)
- [PIC18F47Q10 Code Examples on GitHub](https://github.com/microchip-pic-avr-examples?q=pic18f47q10-cnano&type=&language=)

## Software Used

- MPLAB® X IDE 5.30 or newer [(microchip.com/mplab/mplab-x-ide)](http://www.microchip.com/mplab/mplab-x-ide)
- MPLAB® XC8 2.10 or newer compiler [(microchip.com/mplab/compilers)](http://www.microchip.com/mplab/compilers)
- Microchip PIC18F-Q Series Device Support 1.3.89 or newer [(packs.download.microchip.com/)](https://packs.download.microchip.com/)

## Hardware Used

- PIC18F47Q10 Curiosity Nano [(DM182029)](https://www.microchip.com/Developmenttools/ProductDetails/DM182029)

## Setup

The PIC18F47Q10 Curiosity Nano Development Board is used as the test platform.

<br><img src="images/PIC18F47Q10_CNANO.png" width="600">

The following configurations must be made for this project:

- Clock:
    - Oscillator Select: HFINTOSC
    - HF Internal Clock: Select 1_MHz
    - Clock Divider: 1
- Watchdog Timer: disabled
- Low-voltage Programming: enabled

|Pin           | Configuration      |
| :----------: | :----------------: |
|RA0           | Digital Input      |
|RE0 (LED0)    | Output             |


The RA0 will be connected to the user button using a wire.

## Operation

1. Connect the board to the PC.

2. Open the *pic18f47q10-cnano-gpio-int-bare.X* project in MPLAB® X IDE.

3. Set *pic18f47q10-cnano-gpio-int-bare.X* project as main project. Right click on the project in the *Projects* tab and click *Set as Main Project*:

<br><img src="images/gpio-int-main-project.png" width="400">

4. Select the *PIC18F47Q10 Curiosity Nano* in the *Hardware Tool* section of the project settings:
  - Right click on the project and click *Properties*;
  - Select the *PIC18F47Q10 Curiosity Nano* (click on the SN) in the *Hardware Tool* tab and then click *OK*:

<br><img src="images/gpio-int-project-properties.PNG" width="700">

5. Program the project to the board: right click on the project and click *Make and Program Device*:

<br><img src="images/gpio-int-make-and-program-device.png" width="400">

Result:

<img src="images/demo.gif" alt="Demo" width="500"/>

## Summary 

This project showcases how the General Purpose Input/Output pins on the PIC18F47Q10 can be used as inputs and outputs in order to receive an Interrupt-on-Change and drive an LED high or low.
