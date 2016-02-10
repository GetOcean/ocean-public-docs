---
layout: page
title: Prerequisites for Linux
group: navigation
---
Generally speaking, the Ocean is designed for people who are used to communicating with external computers via the `ssh` command line utility, copying files with `scp`, and communicating with serial devices with a program like `screen` or `minicom`.  The rest of this documentation site will assume you have installed these programs.

If you have these tools installed, then you should not need to do anything further.  If not, read on!

## Installing prerequisites on Ubuntu or Debian

Almost all flavors of Ubuntu or Debian will have the tools required by default.

If not, use the following command to install the required packages via apt-get:

    apt-get install ssh screen minicom


## Checking for pre-installed programs

If you're not sure if you have the required tools:

    $ which screen && which ssh && which scp

You should get something to the following output if all of the required programs are installed:

    /usr/bin/screen
    /usr/bin/ssh
    /usr/bin/scp

If you have got to this point, you should be ready to proceed to other sections in this document.
