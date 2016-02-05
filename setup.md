---
layout: page
title: Ocean Quick Start
group: navigation
tagline:
---
This aim of this guide is to help you set up a new Ocean in less than five minutes.  After working through this guide, your Ocean will be connected to your WiFi network, and you should be able to access it via `ssh`.

# A note on the Ocean

Ocean is a computer running the [Linux operating system](https://en.wikipedia.org/wiki/Linux).  The Ocean is set up to function like a traditional Linux server, in that you do not interact with the Ocean via a screen or mouse.  Instead, you connect to the device with a remote terminal over a network.

However, since our device does not contain a direct ethernet port, the method for doing this involves


# Prerequisites

You need to install a terminal program, capable of communicating with a USB modem.  On Mac OSX, you can install the screen program using [Home Brew](https://brew.sh/):

    brew install screen

Now you are ready to go!

# Steps for setting up your Ocean with a USB terminal

## 1. Power on the Ocean

Hold the top button on the top panel of the Ocean, in the middle of the blue logo, for at least two seconds.  When the Ocean powers on, two red lights will begin glowing on the internal panel, and a green lightshow will

## 2. Connect the USB cable

Plug the micro-USB connector to your Ocean, and then plug the standard USB connector to your computer.


## 3. Wait for the power button to glow white

The power button contains a small LED light that will glow once the OS is ready to talk to your computer using the `screen` program.

## 4. Verify that your computer can detect the Ocean

On your terminal, type the following:

    ls /dev/tty.usbmodem*

If your Ocean is powered on, you have a USB connection between the Ocean and your computer, and the USB cable is working correctly, you should see something like the following:

    /dev/tty.usbmodem1411

NOTE: if you have more than one Ocean, or more than one UBS modem device, attached to your computer, then you will obviously see more than one listing!

## 5. Start the `screen` program

Type the following into your console:

    screen `ls /dev/tty.usbmodem*`

Alternatively, if you have more than one USB modem device connected, copy your preferred USB modem device name into the terminal prompt after `screen`, for example:

    screen /dev/tty.usbmodem1411

When screen starts, you will see a *blank screen*.  This is expected behavior!

## 6. Start the Ocean login prompt

While in screen, type the following:

    bypass

Two things will happen after this.  The power button light will change color, from white to blue.  Also, You should see standard linux login prompt:

    $ bypass
    ev s1

    Debian GNU/Linux 8 FineRock ttyS2

    FineRock login:

Note that every Ocean device has a unique name assigned to it.  `FineRock` is the name of the test device we used to create this document.  Your device will have a different name.


## 7. Login to your Ocean

The initial username and password is the following:

Username: `root`
Password: `alpine`

When you login with these entries, a setup program will run on the Ocean, prompting you to change your password, and to setup a WiFi network:

    FineRock login: root
    Password:


## 8. Follow the steps in the setup program

When you login to your Ocean for the first time, a program will running asking you to change your root password, and optionally select a WiFi network to connect the Ocean to.  *Setting up WiFi network is strongly recommended!*

The setup program will first prompt you to change your root password, like so.

    Welcome to Ocean! Let's update your password and setup your WiFi.
    Let's change your Ocean's password first.
    Enter your new PASSWORD [ENTER]:

You'll be asked to type the new password twice.

    Retype your new PASSWORD [ENTER]:

Next, you will be asked to connect to a WiFi router.  The program will automatically detect WiFi routers that your Ocean can access:

    Great! Your Ocean's password is now changed. Next, let's setup your WiFi.
    Would you like to setup your WiFi? [Y/n]:

You can enter `n` if you'd prefer to type in the name of a hidden WiFi router.

    Would you like to setup your WiFi? [Y/n]: y
    Scanning for networks ...                    
        1. ESSID:"Ocean Home"
        2. ESSID:"Ocean Guest"
        3. ESSID:"Android Hotspot"
    Is your WiFi network visible? [Y/n]: y
    Enter the number of the network you want to connect to [ENTER]: 1
    Your about to attempt to connect to the "Ocean Home" network. Continue? [Y/n]: y
    Enter the PASSWORD for the "Ocean Home" network [ENTER]:
    Retype your PASSWORD for the "Ocean Home" network [ENTER]:

You may need to wait for up to a minute for your Ocean to establish a connection with your chosen network.

    Please wait while we attempt to connect you to the network...

Once the connection has been established, you will see the following messages:

    You have successfully connected to Network "Ocean Home".
    Your device's IP is 10.0.30.64 .
    Run 'wifi-setup start' at any time to setup another WiFi address.
    Enjoy using your Ocean :)

Finally, you'll receive a standard terminal prompt:

    root@FineRock:~#

## 9. Exit setup mode

To exit setup mode, tap the power button again.  The light will disappear, and the Ocean will restart itself to complete the setup process.

Your Ocean is now set up and ready to use!

# Next steps

Use `ssh` to connect to your Ocean.
