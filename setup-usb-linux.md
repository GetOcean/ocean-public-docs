---
layout: page
title: Setup Ocean over USB on Linux
group: navigation
---
This aim of this guide is to help you set up a new Ocean in less than five minutes.  After working through this guide, your Ocean will be connected to your WiFi network, and you should be able to access it via `ssh`.


## Prerequisites for Linux

To install `screen` on Ubuntu, Debian, or other Debian-based operating systems:

    apt-get install screen

On Fedora:

    yum install screen

There are also instruction on how to compile and install `screen`, directly from source, [here](http://www.linuxfromscratch.org/blfs/view/svn/general/screen.html).


## 1. Power on the Ocean and connect the USB

{% include setup/power.md %}

## 2. Start the `screen` program

We use the previously installed `screen` program to talk to the Ocean over a USB modem interface.  `screen` is typically  used in the following way:

    screen $DEVICE_NAME

where `$DEVICE_NAME` is the name of the USB modem interface, as determined by the OS.  The name of the interface can have several different values, depending on your distribution.  On Ubuntu or Debian, the value will normally be something like `ttyACM0`.  Other distributions may have a value like `ttyUSB0`.

Another way of determining the USB device name is to run `udevadm monitor`, and then plug in the Ocean device to the USB.

Once you have determined the name of the Ocean modem interface, type the following into your console to start `screen`:

    screen $DEVICE_NAME

When screen starts, you will see a *blank screen*.  This is expected behavior!


## 3. Start the Ocean login prompt

{% include setup/bypass.md %}

## 4. Login to your Ocean

{% include setup/login.md %}

## 5. Follow the steps in the setup program

{% include setup/setup-program.md %}

## 6. Exit setup mode

{% include setup/exit.md %}


# Next steps

{% include setup/ssh.md %}
