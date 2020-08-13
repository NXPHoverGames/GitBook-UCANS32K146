# Getting started

## UCANS32K146 Overview

![UCANS32K146 Board](../.gitbook/assets/05433ff4-f06f-454c-be27-e4d43a5b4c15_1_105_c.jpeg)

## Powering the board

There are two options when powering the UCANS32K146. The first option is to connect 5V power to the header pins on the board.

![UCANS32K146 V1 Powered through a modified USB cable on the V5 and GND pins](../.gitbook/assets/img_2496.jpeg)

![UCANS32K146 V2 Note location of 5V PWR IN and polarity](../.gitbook/assets/image%20%2815%29.png)

{% hint style="info" %}
Note: The 5V power header is labeled V5.
{% endhint %}

The second option is to power the board through one of the JST-GH CAN connectors. The middle two pins on the CAN connector are for CAN data, and the outer two are for power. The left-most pin is for 5V, and the right-most pin is for GND.  
  
_&lt;TODO - add pinout of CAN header here. Copy from schematics&gt;_

![UCANS32K146 powered through the JST-GH CAN connector](../.gitbook/assets/renderedimage.jpeg)

## Debugging

For flashing firmware and interfacing with the serial console, a JST-GH J-Link SWD interface is present on the board. It is located on the side of the board next to the CAN connectors. 

![UCANS32K146 connected to the J-Link SWD Debugger](../.gitbook/assets/renderedimage-1.jpeg)

A guide for flashing the firmware to the UCANS32K146 is outlined later in this Gitbook.

## Connecting the board to the CAN bus

_**TODO once CAN setup is confirmed by Landon**_

