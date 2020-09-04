# Building and flashing NuttX

## Toolchain

The online NuttX documentation provides [an overview of possible development environments](https://nuttx.apache.org/docs/latest/introduction/development_environments.html), but the [README file in the main NuttX repository](https://github.com/apache/incubator-nuttx/blob/master/README.md) is also a good starting point. In general you're good to go if you are using Linux with a standard GNU toolchain.

Within the NXP Mobile Robotics team we often use PX4 Autopilot as well. They have their own toolchain preferences \(which are compatible with NuttX\), so we often install their preferred toolchain. This is also easy to do because they provide some scripts that take care of most of the work.

## Building NuttX

Building NuttX is very easy when you have all required tools installed. You just have to select a canned configuration, change the configuration to your liking and just run `make`. If you want to throw away the current configuration and select another configuration you first have to run `make distclean`. That's all.

