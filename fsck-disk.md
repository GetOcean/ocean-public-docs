---
layout: page
title: Fix filesystem errors with fsck
group: navigation
---
This guide explains how to fix filesystem errors on your Ocean.  File

You can only run `fsck` on either unmounted, or readonly partition.  When the Ocean is booted, we cannot unmount the OS partition.  Instead, we will need to mount it in readonly mode, fix issues, and then restore the original settings.

# Preparation

When mounting your partition in readonly mode, your WiFi chip will most likely not work. This guide is best followed steps using the USB console interface. If you have not already done so, please read the guide on how to use [USB console]({{ site.baseurl }}/setup-usb) interface before continuing.

## Mounting disk as readonly

Start by finding the `UUID` of your partition. This can be done by running `blkid`, which should return something similar to:

    $ blkid
    /dev/mmcblk0: PTUUID="493c2a7b" PTTYPE="dos"
    /dev/mmcblk0p1: SEC_TYPE="msdos" LABEL="boot" UUID="D331-6AEB" TYPE="vfat" PARTUUID="493c2a7b-01"
    /dev/mmcblk0p2: LABEL="system" UUID="f8023c7c-8765-4780-ab74-0abccd0b3113" TYPE="ext4" PARTUUID="493c2a7b-02"

You are looking for the UUID of `/dev/mmcblk0p2` partition. In the example above, my UUID is `f8023c7c-8765-4780-ab74-0abccd0b3113`.

Next, edit `/etc/fstab` with a text editor such as `nano` or `vim`. I suggest comment out anything that my be present. Copy and paste the following, replacing the `UUID` with the `UUID` of your partition:

    UUID=f8023c7c-8765-4780-ab74-0abccd0b3113   /   ext4    remount,ro  1   1

Reboot your Ocean to mount the partition as readonly.  When you are in USB console mode, you can do this by pressing the home button.

## Fixing partition and remounting drive

Once you have rebooted your Ocean, and you have logged back into the console, run `fsck`:

    $ fsck -y /dev/mmcblk0p2

Reboot once more (by pressing the home button again) and login again. Now make your root file system readble/writable:

    $ mount -o remount,rw /dev/mmcblk0p2

Restore the default setting of `/etc/fstab` (make sure you remove the reference to readonly mount), and reboot a final time (by, once again, pressing the home button). Congratulations, you've just rescued the file system on your Ocean!
