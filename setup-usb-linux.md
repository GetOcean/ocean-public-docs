---
layout: page
title: Ocean setup over USB on Linux
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

We use the `screen` program to talk to the Ocean over a USB modem interface.  Type the following into your console to start `screen`:

    screen `ls /dev/tty.usbmodem*`

When screen starts, you will see a *blank screen*.  This is expected behavior!

If you have more than one USB modem device connected, you need to find the device name of the USB modem running on the Ocean.  Type the following into the console:

    ls /dev/tty.usbmodem*

Next, copy your preferred USB modem device name into the terminal prompt after `screen`, for example:

    screen /dev/tty.usbmodem1411

If you're not sure about the name of your USB modem.


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
