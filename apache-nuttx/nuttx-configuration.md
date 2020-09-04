---
description: >-
  NuttX offers a wide range of configuration options and features that can be
  enabled with one of the available Kconfig frontends.
---

# NuttX configuration

## Install Kconfig frontends

NuttX uses a similar configuration system as the Linux kernel. There are Kconfig files that define the different options and you can generate a configuration file that can be used by the build system with a Kconfig frontend.

NuttX provide their own fork/back-up of the Kconfig-frontends, to make sure that they always have access to a compatible version. It is still hosted on their old BitBucket repository. 

First, make sure you have gperf installed:

```bash
sudo apt install gperf
```

Then download the source code by cloning the NuttX Tools repository from BitBucket:

```bash
git clone https://bitbucket.org/nuttx/tools.git
```

Change the working directory to the kconfig-frontends folder:

```bash
cd tools/kconfig-frontends
```

Configure the build to include \(at least\) the menuconfig and qconfig tools. The Kconfig frontends will be installed into the /usr folder. 

```bash
./configure --enable-mconf --enable-qconf --prefix=/usr
```

Now build the tools according to the configuration that we just created:

```text
make
```

And finally install the Kconfig-frontends that we just build from source:

```text
sudo make install
```

Once you have a "default" configuration in place \(we will get to that in a second\), you can edit the configuration with `make menuconfig` or `make qconfig`. Both tools have their pros and cons, just give them a try and see which one you like the most!

{% hint style="success" %}
In Ubuntu 20.04 it is possible to directly install the kconfig-frontends package from the package repositories. You only need to run `apt install kconfig-frontends`.
{% endhint %}

## Start with a canned configuration

Make sure you are inside the "nuttx" folder:

```text
cd ~/src/apache-nuttx/nuttx
```

Then use the configure script to select the "nshdebug" configuration for the "rddrone-uavcan146" board:

```text
./tools/configure.sh rddrone-uavcan146:nshdebug
```

Make sure to first run `make distclean` if you still have another active configuration.

## Configuration

Menuconfig is the "default" tool to configure the NuttX build. Once you have a board configuration selected \(see above\) you can edit the configuration with:

```text
make menuconfig
```

You can also use qconfig, which shows the configuration as a nested list instead of different menus. This might make it a bit easier to navigate through the many options that are available:

```text
make qconfig
```

Menuconfig and qconfig are easy to use tools, but NuttX is very configurable and you can easily got lost in the hundreds of menus and options that it provides. Take your time to explore the options that NuttX has to offer, but don't try to enable many options at once. Just select a few, build the code and give it a try on the hardware itself.

