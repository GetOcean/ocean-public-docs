---
layout: page
title: Setup Ocean over USB on OSX
group: navigation
---
This aim of this guide is to help you set up a new Ocean in less than five minutes, using USB on OSX.  After working through this guide, your Ocean will be connected to your WiFi network, and you should be able to access it via `ssh`.

## Prerequisites on Mac OSX

Make sure you've gone through the [Prerequisites for OSX]({{ site.baseurl }}/prerequisites-osx) before starting with this section.


## Step 1. Power on the Ocean and connect the USB

{% include setup/power.md %}

## Step 2. Start the `screen` program

We use the `screen` program to talk to the Ocean over a USB modem interface.  `screen` use a device name to connect to the device, but we first have to find the name of the device.  Type the following into your console to find out what device to connect to:

```console
$ ls /dev/tty.usbmodem*
```

If your Ocean is connected, you should get something like the following.  This is the name of the device we'll use when starting `screen`:

```console
/dev/tty.usbmodem1421
```

Copy the device name, the paste it in the `screen` command like this:

```console
$ screen /dev/tty.usbmodem1421 115200
```

If you still have trouble starting `screen` on OSX, [check the troubleshooting section](#trouble).

<div class="alert alert-danger fade in">
  <h4>IMPORTANT NOTE ABOUT SCREEN!</h4>
  <p>When <code>screen</code> starts successfully, <strong>everything on your terminal window will disappear!</strong></p>
  <p>This is expected behavior! Keep going!</p>
</div>


## Step 3. Start the Ocean console

{% include setup/bypass.md %}

## Step 4. Login to your Ocean

{% include setup/login.md %}

## Step 5. Follow the steps in the setup program

{% include setup/setup-program.md %}

## Step 6. Exit setup mode

{% include setup/exit.md %}


<a name="trouble"></a>

# Troubleshooting

## OSX: `screen` won't start

Verify that your computer can detect the Ocean.  On your terminal, type the following:

```console
$ ls /dev/tty.usbmodem*
```

If your Ocean is powered on, you have a USB connection between the Ocean and your computer, and the USB cable is working correctly, you should see something like the following:

```console
/dev/tty.usbmodem1411
```

## OSX: `screen` starts, but it shows an error message and shuts down!

There are two things to do in this situation:

* Close your current console window and open another one.
* Unplug the USB cable, and plug it back in again.

## OSX: I have more than one USB modem device attached

If you have more than one USB modem device connected, you need to find the device name of the USB modem running on the Ocean.  Type the following into the console:

```console
$ ls /dev/tty.usbmodem*
```

Disconnect your device, and re-run `ls /dev/tty.usbmodem*` to find the name of the device.  The device that connected should no longer show in the list.  You can then deduce the name of the device name to use with screen by disconnecting and reconnecting device while running `ls /dev/tty.usbmodem*` (if you know of a better way of doing this, [please let us know](mailto:davidp@icracked.com).

Next, copy your preferred USB modem device name into the terminal prompt after `screen`, for example:

```console
$ screen /dev/tty.usbmodem1412 115200
```


# Next steps

[Connect to your Ocean with ssh]({{ site.baseurl }}/connect-with-ssh-osx)
