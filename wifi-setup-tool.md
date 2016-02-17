---
layout: page
title: Add Another WiFi Network with 'wifi-setup'
group: navigation
---

`wifi-setup` is a command line tool you can use to easily add another WiFi network address and password to your Ocean.

## Walkthrough

### Step 1: Start `wifi-setup`

Run `wifi-setup` like this:

```console
$ wifi-setup start
```

You should see the following:

```console
$ wifi-setup start
This script will help you setup your WiFi credentials.
Would you like to setup your WiFi? [Y/n]:
```

Type `Y` to move to the next step, where available networks will automatically be scanned:

### Step 2: Choose a Network

```console
$ wifi-setup start
This script will help you setup your WiFi credentials.
Would you like to setup your WiFi? [Y/n]: Y
Scanning for networks ...
        1. Office Router
        2. Cafe Wifi
        3. Neighborhood Router
Is your WiFi network visible? [Y/n]:
```

Type `Y` if your expected network is visible, or `n` to rescan.  If `Y`, you'll see the following:

```console
Enter the number of the network you want to connect to [ENTER]: 2
Connect to "Cafe Wifi" network now? [Y/n]:
```

If you answer `Y` you'll be asked to enter your network password.  If you enter `n` you will be taken back to the network list to choose another network to connect to.

### Step 3: Enter your Network Password

You'll be asked for your password twice.  When you type, your password will not be visible:

```console
Enter your PASSWORD for the "Cafe Wifi" network [ENTER]:
Retype your PASSWORD for the "Cafe Wifi" network [ENTER]:
```

### Step 4: Wait for the Ocean to Connect

If you entered the password correctly twice, you should see the following:

```console
Please wait while we attempt to connect you to the network...
```

Once the connection has been established, you will see the following messages:

```console
You have successfully connected to Network "Cafe Wifi".
Your device's IP is 10.0.30.64.
Run 'wifi-setup start' at any time to setup another WiFi address.
Enjoy using your Ocean :)
```

### Step 5: (Optional) Test Your Internet Connection

If your WiFi router is connected to the internet, you can ping Google to see if your Ocean can reach a Google server:

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

If you did not get a result like this, check the next guide for [setting up WiFi manually with `wpa_supplicant`]({{ site.baseurl }}/wifi-wpa-supplicant).
