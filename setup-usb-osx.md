---
layout: page
title: Setup Ocean over USB on OSX
group: navigation
---
This aim of this guide is to help you set up a new Ocean in less than five minutes, using USB on OSX.  After working through this guide, your Ocean will be connected to your WiFi network, and you should be able to access it via `ssh`.

## Prerequisites on Mac OSX

You need to install a terminal program, capable of communicating with a USB modem.  On Mac OSX, you can install the screen program using [Home Brew](https://brew.sh/):

    brew install screen

Once your've installed screen, ensure that it installed correctly:

    $ which screen
    /usr/bin/screen


## 1. Power on the Ocean and connect the USB

{% include setup/power.md %}

## 2. Start the `screen` program

We use the `screen` program to talk to the Ocean over a USB modem interface.  Type the following into your console to start `screen`:

    screen `ls /dev/tty.usbmodem*`

When screen starts, you will see a *blank screen*.  This is expected behavior!

If you have more than one USB modem device connected, you need to find the device name of the USB modem running on the Ocean.  Type the following into the console:

    ls /dev/tty.usbmodem*

Next, copy your preferred USB modem device name into the terminal prompt after `screen`, for example:

    screen /dev/tty.usbmodem1411


## 3. Start the Ocean login prompt

{% include setup/bypass.md %}

## 4. Login to your Ocean

{% include setup/login.md %}

## 5. Follow the steps in the setup program

{% include setup/setup-program.md %}

## 6. Exit setup mode

{% include setup/exit.md %}



## Troubleshooting: OSX: `screen` won't start

Verify that your computer can detect the Ocean.  On your terminal, type the following:

    ls /dev/tty.usbmodem*

If your Ocean is powered on, you have a USB connection between the Ocean and your computer, and the USB cable is working correctly, you should see something like the following:

    /dev/tty.usbmodem1411

NOTE: if you have more than one Ocean, or more than one UBS modem device, attached to your computer, then you will obviously see more than one listing!


# Next steps

[Connect to your Ocean with ssh]({{ site.baseurl }}/connect-with-ssh-osx)
