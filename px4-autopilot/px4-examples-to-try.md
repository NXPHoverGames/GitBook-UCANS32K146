# PX4 examples to try

Assuming you have successfully connected via the UART and are seeing the PX4/NuttX nsh&gt; prompt, you can try a few things using PX4/NuttX  


```text
nsh> help
```

This will show you basic help as well as list the Builtin Apps.

Try running some of the builtin apps: \(Lines beginning with \# below are just comments\)

```text
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

