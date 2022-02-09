# PX4 examples to try

Assuming you have successfully connected via the UART and are seeing the PX4/NuttX nsh> prompt, you can try a few things using PX4/NuttX\


```
nsh> help
```

This will show you basic help as well as list the Builtin Apps.

Try running some of the builtin apps: (Lines beginning with # below are just comments)

```
nsh> #run hello world
nsh> hello

nsh> #control the onboard RGB LED 
nsh> led_control breathe -c cyan

nsh> #check the actual RGB PWM driver status
nsh> rgbled_pwm status

nsh> #view the rtos processes
nsh> top

nsh> #check the hardware version and git verion
nsh> ver hw
nsh> ver git
```

As you can see there are also a number of other builtin apps ready to test servo's, I2C devices, SPI devices, and even a GPS when attached.

## Testing CAN between two UCANS32K146 boards using PX4 CAN utilities

If you followed the instructions on the previous page to enable CAN utilities in PX4, then follow the steps below to test CAN communication between the boards.

1. Connect two UCANS32K146 boards with the included CAN cable (yellow and white twisted pair with red and black power lines)
2. Connect a termination resistor to each board on the same bus
3. Boot up each board and connect to them using the included debuggers
4. On each board, run `ifup can0` if using the CAN1 bus, or `ifup can1` if using the CAN2 bus
5. On one board, run `candump can0` or `candump can1` depending on what bus you are using
6. On the other board, run `cansend can0 123#deadbeef` to test CAN traffic. You should see the CAN message show up on the receiving board.
7. You have successfully tested CAN communication on UCANS32K146.

