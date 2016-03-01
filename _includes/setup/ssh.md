If you've setup Wifi on your Ocean, you should be able to connect to your Ocean with the `ssh` program.  If you haven't already done so, [here are the instructions for setting up WiFi on your Ocean](https://getocean.io/docs/getting-started).

In another terminal window, type the following (replace the IP address with the IP address you were given by the Ocean WiFi setup program):

```console
# ssh root@10.0.30.64
```

You will be prompted to enter your password:

```console
root@10.0.30.64's password:
```

Type in the same password you specified in Step 5.  If it you entered the password correctly, you should see the following output:

```console
The programs included with the Debian GNU/Linux system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Debian GNU/Linux comes with ABSOLUTELY NO WARRANTY, to the extent
permitted by applicable law.
Last login: Wed Feb  3 17:24:52 2016 from 10.0.1.111
root@FineRock:~#
```

You now have console access to your Ocean on your wireless network.  Awesome!

### IMPORTANT Secure Your Ocean!

Once you have successfully connected to your Ocean via `ssh`, please [follow the instructions here for securing your Ocean]({{}}/securing-your-ocean).
