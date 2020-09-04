# Building the PX4 firmware

## Prerequisites

If you aren't using the HoverGames virtual machine and haven't already cloned the PX4 firmware on your device, you'll need to do so by running the following command:

```text
git clone https://github.com/PX4/Firmware
```

## Building the PX4 firmware for UCANS32K146

{% hint style="danger" %}
NOTE: PX4 firmware for the UCANS32K146 is not fully developed yet. The steps below are not guaranteed to work as of 6/5/2020.
{% endhint %}

To build the PX4 firmware for the UCANS32K146, you'll need to run the following command:

```text
make nxp_rddrone-uavcan146
```

in the root directory where you cloned the PX4 firmware. The .bin file for flashing the firmware will be stored in `[Firmware Root]/build/nxp_rddrone-uavcan146_default/`. The file you're looking for is `nxp_rddrone-uavcan146.bin`. You can leave the file there or copy it to another location for flashing the board in the next section.

