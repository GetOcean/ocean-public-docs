---
layout: page
title: Prerequisites for OSX
group: navigation
---
Generally speaking, the Ocean is designed for people who are used to communicating with external computers via the `ssh` command line utility, copying files with `scp`, and communicating with serial devices with a program like `screen` or `minicom`.  The rest of this documentation site will assume you have installed these programs.

If you have these tools installed, then you should not need to do anything further.  If not, read on!

## Using the terminal

You need access to the terminal program.  OSX application can be found in the *Applications/Utilties* folder, here:

![Location of Terminal on OSX]({{ site.baseurl }}/assets/images/Terminal_OSX.png)

Alternatively, you can use *Spotlight* to instantly start the program.  Hit *Command-Space* on you keyboard, and then type in `Terminal`, like this:

![Terminal on Spotlight on OSX]({{ site.baseurl }}/assets/images/Spotlight-terminal.png)

Once you start Terminal, it should look something like this:

![Terminal]({{ site.baseurl }}/assets/images/terminal2_osx.png)


## Checking for pre-installed programs

Type the following to check that you have access to the required tools:

    $ which screen && which ssh && which scp

You should get something to the following output if all of the required programs are installed:

    /usr/bin/screen
    /usr/bin/ssh
    /usr/bin/scp

If you have got to this point, you should be ready to proceed to other sections in this document.

## Installing missing programs

Most flavors of OSX will come with all of the required tools for communicating with an Ocean.  If they're missing, we assume you know what you are doing and know how to re-instate them again.

## Other useful stuff

There's a great guide here that will tell you how to install `minicom`: [Macs and serial TTYs](http://pbxbook.com/other/mac-tty.html)

Here's a great guide for setting up a version of `screen` that uses 256 colors: [Installing GNU Screen on OS X in Homebrew](https://gist.github.com/bigeasy/2327150)
