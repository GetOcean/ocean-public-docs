---
layout: page
title: Fix (fsck) your disk
group: navigation
---

You can only run `fsck` on either unmounted, or readonly partition. Since we cannot unmount are OS partition, we will need to mount it as readonly, fix issues, and then restore original setting.

Please note that when mounting your partition as readonly, your WiFi chip will probably not work. Please continue these steps using the USB Console interface. Please read the guide on how to use [USB console]({{ site.baseurl }}/setup-usb) interface before continuing.

## Mounting disk as readonly

Start by finding the `UUID` of your partition. This can be done by running `blkid`, which should return something similar to:

    /dev/mmcblk0: PTUUID="493c2a7b" PTTYPE="dos"
    /dev/mmcblk0p1: SEC_TYPE="msdos" LABEL="boot" UUID="D331-6AEB" TYPE="vfat" PARTUUID="493c2a7b-01"
    /dev/mmcblk0p2: LABEL="system" UUID="f8023c7c-8765-4780-ab74-0abccd0b3113" TYPE="ext4" PARTUUID="493c2a7b-02"

You are looking for the UUID of `/dev/mmcblk0p2` partition. In the example above, my UUID is `f8023c7c-8765-4780-ab74-0abccd0b3113`.

Next, edit `/etc/fstab` with your favourite editor. I suggest comment out anything that my be present. Copy and paste the following, replacing the `UUID` with the `UUID` of your partition:

    UUID=f8023c7c-8765-4780-ab74-0abccd0b3113   /   ext4    remount,ro  1   1

Reboot your Ocean (by pressing the home button to exit bypass mode) to mount the partition as readonly.

## Fixing partition and remounting drive

Once you rebooted your computer and logged back into the console, run `fsck`:

    fsck -y /dev/mmcblk0p2

Reboot once more (by pressing the home button to exit bypass mode) and login again. Now make your root file system readble/writable:

    mount -o remount,rw /dev/mmcblk0p2

Restore the default setting of `/etc/fstab` (make sure you remove the reference to readonly mount), and reboot a final time (by pressing the home button to exit bypass mode). Congratulations, you've just rescued your Ocean!
