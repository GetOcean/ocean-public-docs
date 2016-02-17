---
layout: page
title: Add Another WiFi Network with 'wpa_supplicant'
group: navigation
---

`wpa_supplicant` is a WiFi configuration utility.

## Walkthrough

### Step 1: Edit Configuration Files

Use an editor to modify the file at the following location:

```
/etc/wpa_supplicant/wpa_supplicant.conf
```

Next, copy and paste the following into your `wpa_supplicant.conf` file, replacing `SSID` with the full name of the network you wish to connect to, and `PASSWORD` with the password of the network:

```kconfig
network={
    ssid="SSID"
    psk="PASSWORD"
    proto=RSN
    key_mgmt=WPA-PSK
    pairwise=CCMP TKIP
    group=CCMP TKIP
}
```

The above settings will work best for networks using WPA2 security.  For different network settings, check the wpa_supplicant `man` page.

```console
$ man wpa_supplicant
```

SHORTCUT: In the following command, replace `SSID` with the full name of the network you wish to connect to, and `PASSWORD` with the password of the network:

```console
$ wpa_supplicant "SSID" "PASSWORD" >> /etc/wpa_supplicant/wpa_supplicant.conf
```

This will append the network info to the end of the `wpa_supplicant` configuration file.

### Step 2: Restart Networking

Use `ifup` to bring up the wlan0 interface:

```console
$ ifup wlan0
```

If this doesn't work, you may need to cycle `wlan0`, like this:

```console
$ ifdown wlan0
$ ifup wlan0
```

### Step 3: Check `iwconfig` and `ifconfig`

The utilities will print out information about your connection.  `iwconfig` will look something like this when you have successfully connected to the network:

```console
$ iwconfig
lo        no wireless extensions.

tunl0     no wireless extensions.

wlan0     IEEE 802.11  ESSID:"My Network"
          Mode:Master  Frequency:2.437 GHz  Access Point: 02:18:4A:05:F7:42
          Bit Rate=52 Mb/s   Tx-Power:32 dBm
          Retry min limit:7   RTS thr:off   Fragment thr:off
          Encryption key:off
          Power Management:off

bond0     no wireless extensions.

p2p0      IEEE 802.11bgn  ESSID:off/any
          Mode:Managed  Access Point: Not-Associated   Tx-Power=1496 dBm
          Retry  long limit:7   RTS thr:off   Fragment thr:off
          Encryption key:off
          Power Management:on
```

`ifconfig` should report an IP address for `wlan0` if you've successfully connected to the router:

```console
$ ifconfig
lo       Link encap:Local Loopback
         inet addr:127.0.0.1  Mask:255.0.0.0
         UP LOOPBACK RUNNING  MTU:16436  Metric:1
         RX packets:368 errors:0 dropped:0 overruns:0 frame:0
         TX packets:368 errors:0 dropped:0 overruns:0 carrier:0
         collisions:0 txqueuelen:0
         RX bytes:103453 (101.0 KiB)  TX bytes:103453 (101.0 KiB)

wlan0    Link encap:Ethernet  HWaddr 00:22:f4:f7:c6:5b
         inet addr:10.0.30.57  Bcast:10.0.255.255  Mask:255.255.0.0
         UP BROADCAST RUNNING MULTICAST  MTU:1500  Metric:1
         RX packets:10905 errors:0 dropped:0 overruns:0 frame:0
         TX packets:110 errors:0 dropped:0 overruns:0 carrier:0
         collisions:0 txqueuelen:1000
         RX bytes:2761564 (2.6 MiB)  TX bytes:11720 (11.4 KiB)
```

If neither of these commands produce useful output, you may need to restart networking completely:

```console
$ /etc/init.d/networking restart
```

### Step 4: (Optional) Test Your Internet Connection

As in the guide for setting up WiFi with the If your WiFi router is connected to the internet, you can ping Google to see if your Ocean can reach a Google server:

```console
$ ping -c 4 www.google.com
```

You should see something similar to the following

```console
$ ping -c 4 www.google.com
PING www.google.com (216.58.216.132) 56(84) bytes of data.
64 bytes from sea15s01-in-f4.1e100.net (216.58.216.132): icmp_seq=1 ttl=54 time=20 1 ms
64 bytes from sea15s01-in-f4.1e100.net (216.58.216.132): icmp_seq=2 ttl=54 time=23.7 ms
64 bytes from sea15s01-in-f4.1e100.net (216.58.216.132): icmp_seq=3 ttl=54 time=21.3 ms
64 bytes from sea15s01-in-f4.1e100.net (216.58.216.132): icmp_seq=4tttl=54 time=20.8 ms

--- www.google.com ping statistics ---
4 packets transmitted, 4 received, 0% pack l loss, time 3005ms
rtt min/avg/max/mdev = 20.168/21.519/23.750/1.361 ms
```
