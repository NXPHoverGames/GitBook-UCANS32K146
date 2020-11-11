---
description: >-
  NuttX is an embedded RTOS with an emphasis on standards compliance and small
  footprint.
---

# About Apache NuttX

## What is NuttX?

> NuttX is a real-time operating system \(RTOS\) with an emphasis on standards compliance and small footprint. Scalable from 8-bit to 32-bit microcontroller environments, the primary governing standards in NuttX are Posix and ANSI standards. Additional standard APIs from Unix and other common RTOS’s \(such as VxWorks\) are adopted for functionality not available under these standards, or for functionality that is not appropriate for deeply-embedded environments \(such as fork\(\)\). -- _****_[_**Apache NuttX website**_](https://nuttx.apache.org/)_\*\*\*\*_

NuttX was created by Gregory Nutt and he has been one of the main developers for a very long time.   
In 2019 the RTOS was accepted as an incubating project under the Apache Software Foundation, which means it is currently undergoing the process to become an official ASF project. There is now a management committee in place that oversees the ongoing development of NuttX.

NuttX is a very versatile operating system with many \(optional\) features that supports a wide range of microcontroller platforms. This includes support for NXP's S32K1xx and i.MX RT 10xx, as well as many MCUs from the Kinetis and LPC families.

NuttX is licensed under the permissive Apache License 2.0. This allows it to be integrated into other projects without the need to distribute the derivative work under the same license. Parts of the codebase may still be licensed under the BSD 3-clause license that was used previously, but this should not pose any limitations.

## NuttX support for UCANS32K146

A board configuration for RDDRONE-UCANS32K146 is available in the upstream Apache NuttX repositories. As of September 2020, the following features are confirmed to be available:

* Basic support for the NXP S32K1xx family \(ARM Cortex-M0+ and M4F\)
* SPI, I2C and UART are enabled and can be used in your own drivers and applications
* PWM output using the FlexTimer peripheral is available as well

There is currently no driver support in NuttX for the NXP EdgeLock SE050 secure element.

## PX4, NuttX or bare-metal?

[PX4 Autopilot](https://docs.px4.io/master/en/) is build on top of NuttX, so most of the features that are available in NuttX are also available if you choose to [run PX4 on the UCANS32K146](../px4-autopilot/about-px4.md). PX4 uses most interfaces that NuttX provides, but adds additional abstractions and in some cases it bypasses the NuttX interfaces and implements its own API. So there's some differences, but you still get most of the features of NuttX, as well as PX4's [uORB publish/subscribe messaging API](https://dev.px4.io/master/en/middleware/uorb.html), their [parameter system](https://dev.px4.io/master/en/advanced/parameters_and_configurations.html), as well as many [drivers for sensors and actuators](https://dev.px4.io/master/en/middleware/modules_driver.html).

However, if you do not plan on using any of the PX4 features and do not need to interface with any other PX4-enabled system, you can also use the UCANS32K146 development board with "just" NuttX. This makes it easier to [customize the configuration and enable features](nuttx-configuration.md) to your liking without having to worry about breaking the PX4 stack.

There is also a third option. NXP offers a "bare-metal" SDK for the S32K1xx family, and [there is also a bare-metal libUAVCAN implementation available](../s32k1-sdk/sdk-example-with-uavcan.md). That means you can use the UCANS32K146 board with UAVCAN, but without any operating system or software stack. Or you can integrate it with other software.

## Documentation and getting help

Documentation for NuttX is available on their website:

* [https://nuttx.apache.org/](https://nuttx.apache.org/)
* [https://nuttx.apache.org/docs/latest/](https://nuttx.apache.org/docs/latest/)
* [https://cwiki.apache.org/confluence/display/NUTTX/Documentation](https://cwiki.apache.org/confluence/display/NUTTX/Documentation)

Their online documentation is not exactly beginner friendly. A few volunteers have stepped forward to help improve the available documentation, but there is still some work to be done. Luckily, the code base is pretty clean and self explanatory \(and often well documented within the code itself\). With a few pointers in the right direction and some patience you can get pretty far on your own. 

The community page on the official Apache NuttX website lists a few ways to ask questions, report issues and get in contact with the main developers:

* [https://nuttx.apache.org/community/](https://nuttx.apache.org/community/)

