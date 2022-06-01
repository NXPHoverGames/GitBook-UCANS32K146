# Getting started

## UCANS32K146 overview

![RDDRONE-UCANS32K146 front view](.gitbook/assets/ucans32k146\_front.png)

![RDDRONE-UCANS32K146 back view](.gitbook/assets/ucans32k146\_back.png)

## Powering the board

There are two options when powering the UCANS32K146. The first option is to connect 5V power to the power pins on the board. The second option is to power the board through one of the JST-GH CAN connectors. The middle two pins on the CAN connector are for CAN data, and the outer two are for power. The left-most pin is for 5V, and the right-most pin is for GND.

![Two options for powering UCANS32K146.](.gitbook/assets/ucans32k146.jpg)

![UCANS32K146 (pre-production) powered through the JST-GH CAN connector](.gitbook/assets/RenderedImage.jpeg)

## Flashing and debugging

For flashing firmware and interfacing with the serial console, a 7-pin JST-GH connector with SWD and UART interfaces is present on the board. It is located on the side of the board next to the CAN connectors.&#x20;

![UCANS32K146 (pre-production) connected to a debugger breakout boards.](.gitbook/assets/RenderedImage-1.jpeg)

Guides for flashing binaries to UCANS32K146 are available for [PX4 Autopilot](px4-autopilot/building-and-flashing-px4.md#flashing-px4-autopilot-to-the-ucans-32-k146-board) and Apache NuttX.
