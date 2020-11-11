# Building and flashing NuttX

## Toolchain

The online NuttX documentation provides [an overview of possible development environments](https://nuttx.apache.org/docs/latest/introduction/development_environments.html), but the [README file in the main NuttX repository](https://github.com/apache/incubator-nuttx/blob/master/README.md) is also a good starting point. In general you're good to go if you are using Linux with a standard GNU toolchain.

Within the NXP Mobile Robotics team we often use PX4 Autopilot as well. They have their own toolchain preferences \(which are compatible with NuttX\), so we often install their preferred toolchain. This is also easy to do because they provide some scripts that take care of most of the work.

## Building NuttX

Building NuttX is very easy when you have all required tools installed. You just have to select a canned configuration, change the configuration to your liking and just run `make`. If you want to throw away the current configuration and select another configuration you first have to run `make distclean`. That's all.

## Flashing NuttX

Download and install the [J-Link Software and Documentation Pack](https://www.segger.com/downloads/jlink#J-LinkSoftwareAndDocumentationPack). It is available for all major operating systems, but we will assume here that you are using a Linux-based OS. Open a terminal and navigate to the main `nuttx` directory, which contains `nuttx.bin` after a successful build. Then you can start the J-Link tools by entering:

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

Now flash the binary with:

```bash
loadbin nuttx.bin 0
```

The binary will be programmed and this process will also be verified. It should then mention if everything went OK. You can quit the J-Link tools with:

```bash
q
```

You may need to power cycle the device afterwards. The debug console should now be available on LPUART1 \(115200 baud\) - which is also accessible on the debugger breakout board.

