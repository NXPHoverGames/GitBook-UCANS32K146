---
description: >-
  PX4 is an open source flight control software for drones and other unmanned
  vehicles.
---

# About PX4 Autopilot

## What is PX4 Autopilot?

> PX4 is an open source flight control software for drones and other unmanned vehicles. The project provides a flexible set of tools for drone developers to share technologies to create tailored solutions for drone applications. PX4 provides a standard to deliver drone hardware support and software stack, allowing an ecosystem to build and maintain hardware and software in a scalable way.
>
> PX4 is part of [Dronecode](https://www.dronecode.org/), a non-profit organization administered by Linux Foundation to foster the use of open source software on flying vehicles. Dronecode also hosts QGroundControl, MAVLink & the SDK. -- [_**PX4 website**_](https://px4.io/software/software-overview/)_\*\*\*\*_

{% hint style="success" %}
PX4 Autopilot for UCANS32K146 is build on top of NuttX. Therefore, most of the information in the "[Apache NuttX](../apache-nuttx/about-apache-nuttx.md#px-4-nuttx-or-bare-metal)" section also applies to PX4! Besides flight control and autopilot software, it also contains additional tools, drivers and middleware.
{% endhint %}

## PX4 support for UCANS32K146

The PX4 development team provides basic support for UCANS32K146. A board configuration is available from which [a binary can easily be build](building-and-flashing-px4.md). Because PX4 is build on top of NuttX, it supports most of the [features that were enabled in the NuttX build](../apache-nuttx/about-apache-nuttx.md#nuttx-support-for-ucans-32-k146) for UCANS32K146.

There are some additional features offered by PX4:

* [uORB and MAVLink messaging](https://dev.px4.io/master/en/middleware/)
* PWM generation
* Most PX4 drivers and modules can be enabled

There is currently no driver support in PX4 or NuttX for the NXP EdgeLock SE050 secure element.

## Documentation and getting help

Documentation for PX4 is available on their website:

* [https://px4.io/](https://px4.io/)
* [https://docs.px4.io/master/en/](https://docs.px4.io/master/en/)
* [https://dev.px4.io/master/en/](https://dev.px4.io/master/en/)

PX4 Autopilot is originally a drone flight control stack, therefore most of the documentation is focused on using PX4 on flight management units. Not all features may be directly available on UCANS32K146, though you can potentially enable all modules in the source code.

Issues can be reported on the [PX4 GitHub](https://github.com/PX4/PX4-Autopilot). There are various [support channels](https://dev.px4.io/master/en/contribute/support.html) available where you can ask questions and discuss your ideas.



