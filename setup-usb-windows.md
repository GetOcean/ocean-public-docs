---
layout: page
title: Setup your Ocean over USB on Windows
group: navigation
---
This aim of this guide is to help you set up a new Ocean in less than five minutes, using USB on Windows.  After working through this guide, your Ocean will be connected to your WiFi network, and you should be able to access it via `ssh`.

## Prerequisites for Windows

`PuTTY` is required for Windows.  PuTTY can be downloaded [from this site](http://www.putty.org/).


## 1. Power on the Ocean

{% include setup/power.md %}

## 2. Start PuTTY

(Coming soon).


## 3. Start the Ocean login prompt

{% include setup/bypass.md %}

## 4. Login to your Ocean

{% include setup/login.md %}

## 5. Follow the steps in the setup program

{% include setup/setup-program.md %}

## 6. Exit setup mode

{% include setup/exit.md %}


## OSX: `screen` won't start

Verify that your computer can detect the Ocean.  On your terminal, type the following:

    ls /dev/tty.usbmodem*

If your Ocean is powered on, you have a USB connection between the Ocean and your computer, and the USB cable is working correctly, you should see something like the following:

    /dev/tty.usbmodem1411

NOTE: if you have more than one Ocean, or more than one UBS modem device, attached to your computer, then you will obviously see more than one listing!


# Next steps

- [Use `ssh` to connect to your Ocean](/connect-with-ssh).
