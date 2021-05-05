---
description: How to build and flash PX4 Autopilot for NXP UCANS32K146.
---

# Building and flashing PX4

## Prerequisites

You need a build environment that can build PX4 Autopilot. You can generally use the [same environment as with Apache NuttX](../apache-nuttx/building-and-flashing-nuttx.md#toolchain), but you will need to install some additional packages. To get started, you can use the [HoverGames virtual machine](https://nxp.gitbook.io/hovergames/developerguide/tools), or install your own Linux \(virtual\) machine. When you have a basic Linux environment, you only need to [install the PX4 toolchain](https://nxp.gitbook.io/hovergames/developerguide/tools/toolchain-installation) to continue. 

More information is also available in the [PX4 Developer Guide](https://dev.px4.io/master/en/setup/getting_started.html).

If you have not yet cloned the PX4 source code as part of the toolchain installation, you should do so now:

```bash
git clone https://github.com/PX4/PX4-Autopilot
```

## Building PX4 Autopilot for UCANS32K146

Change  your working directory \(`cd` command\) to the PX4-Autopilot Git repository that you just cloned. Next we will build the bootloader and firmware for our UCAN board.

### Bootloader

{% hint style="info" %}
You only need to build and flash the bootloader once. If you rebuild/reflash PX4, you can skip all of the bootloader steps.
{% endhint %}

#### Downloading the Bootloader

If you don't want to build the bootloader, you can download it by clicking the file below.

{% embed url="http://ci.px4.io/job/PX4\_misc/job/Firmware-compile/job/master/lastSuccessfulBuild/artifact/build/nxp\_ucans32k146\_default/nxp\_ucans32k146.bin" caption="UCANS32K146 PX4 Bootloader" %}

### Building the Bootloader

To build the bootloader, run:

```bash
make nxp_ucans32k146_canbootloader
```

The binary file will be located at `PX4-Autopilot/build/nxp_ucans32k146_canbootloader/nxp_ucans32k146.bin`. Keep this file handy for flashing later.

### PX4 Firmware

Next, build the firmware by running:

```bash
make nxp_ucans32k146
```

The .bin file for flashing the firmware will be stored in `build/nxp_ucans32k146_default/deploy`. The file you're looking for is `34.bin`. You can leave the file there or copy it to another location for flashing the board in the next section.

A prebuilt version of PX4 for UCANS32K146 is linked below. You should download the file prefixed with `34-0.1`:

{% embed url="http://ci.px4.io/job/PX4\_misc/job/Firmware-compile/job/master/lastSuccessfulBuild/artifact/build/nxp\_ucans32k146\_default/" %}



## Flashing PX4 Autopilot to the UCANS32K146 board

Download and install the [J-Link Software and Documentation Pack](https://www.segger.com/downloads/jlink#J-LinkSoftwareAndDocumentationPack). It is available for all major operating systems, but we will assume here that you are using a Linux-based OS. Open a terminal and navigate to the directory which holds the `nxp_ucans32k146.bin` file that we build in the previous step.

Now start the J-Link tools by entering:

```bash
JLinkExe
```

Make sure that the debugger is plugged into both the UCANS32K146 board and your computer. If you are using a virtual machine, the debugger USB device should be made available inside the VM. Also do not forget to power the board. Now enter:

```bash
connect
```

You are now asked to specify a device. It is quickest to manually enter the device:

```bash
s32k146
```

The target interface needs to be specified, which is SWD:

```bash
s
```

Finally you have to specify the target interface speed. It is recommended to use 1000 kHz:

```bash
1000
```

Now flash the bootloader with:

```bash
loadbin /path/to/nxp_ucans32k146.bin 0x0
```

The binary will be programmed and this process will also be verified. It should then mention if everything went OK. 

Next, flash the PX4 firmware binary with:

```bash
# If using pre-built binary
loadbin /path/to/34-0.1.ac6e7a1c.uavcan.bin 0x6000
# If using self-built binary
loadbin /path/to/34.bin 0x6000
```

And you're good to go.

You can quit the J-Link tools with:

```bash
q
```

You may need to power cycle the device afterwards. The debug console should now be available on LPUART1 \(115200 baud\) - which is also accessible on the debugger breakout board.

## More information

The PX4-build for UCANS32K146 is in an early state and not all features may be available. More information about PX4 Autopilot is available in their [User Guide](http://docs.px4.io/master/en/) and [Developer Guide](https://dev.px4.io/master/en/). Their software development is managed on [GitHub](https://github.com/PX4/PX4-Autopilot). There are also various [support channels](https://dev.px4.io/master/en/contribute/support.html) available.

