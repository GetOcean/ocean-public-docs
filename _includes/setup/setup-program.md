When you login to your Ocean for the first time, a setup program will run automatically.  This program will ask you to change your root password.  It will also, optionally, prompt you to select a WiFi network for the Ocean.  *Setting up a WiFi network is strongly recommended!*

The setup program will first prompt you to change your root password, like so.

```console
Welcome to Ocean! Let's update your password and setup your WiFi.
Let's change your Ocean's password first.
Enter your new PASSWORD [ENTER]:
```

You'll be asked to type the new password twice.

```console
Retype your new PASSWORD [ENTER]:
```

Next, you will be asked to connect to a WiFi router.  The program will automatically detect WiFi routers that your Ocean can access:

```console
Great! Your Ocean's password is now changed. Next, let's setup your WiFi.
Would you like to setup your WiFi? [Y/n]:
```

You can enter `n` if you'd prefer to continue using your Ocean through the USB connection.

```console
Would you like to setup your WiFi? [Y/n]: y
Scanning for networks ...                    
    1. ESSID:"Ocean Home"
    2. ESSID:"Ocean Guest"
    3. ESSID:"Android Hotspot"
Is your WiFi network visible? [Y/n]:
```

You can enter `n` if you'd prefer to type in the name of a hidden WiFi router.

```console
Is your WiFi network visible? [Y/n]: y
Enter the number of the network you want to connect to [ENTER]: 1
You are about to attempt to connect to the "Ocean Home" network. Continue? [Y/n]: y
```

You will next be prompted to type a password for the wifi network you wish to connect to:

```console
Enter the PASSWORD for the "Ocean Home" network [ENTER]:
Retype your PASSWORD for the "Ocean Home" network [ENTER]:
```

You may need to wait for up to a minute for your Ocean to establish a connection with your chosen network.

```console
Please wait while we attempt to connect you to the network...
```

Once the connection has been established, you will see the following messages:

```console
You have successfully connected to Network "Ocean Home".
Your device's IP is 10.0.30.64 .
Run 'wifi-setup start' at any time to setup another WiFi address.
Enjoy using your Ocean :)
```

_Make a note of your IP address above!_  You'll be using it to connect to your Ocean unit in a later step.

Finally, you'll receive a standard terminal prompt:

```console
root@FineRock:~#
```
