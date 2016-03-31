---
layout: page
title: Using 'surf'
group: navigation
---

## Prerequisite
Make sure `surf` is installed by running `which surf`. It should return:

    /usr/local/bin/surf

If you don't see anything, then follow [this guide]({{ sites.baseurl }}/install-surf) to install `surf`.

## Quick Setup
`surf` exposes a port on Ocean to the world. It supports `http, https, tcp` protocls. First run your application on the port of your choice. For instance, you can follow [Set up a static web server on your Ocean]({{ site.baseurl }}/setup-simple-webserver) to setup a simple web server.

Next, run `surf 8080` where `8080` is the port you are trying to expose. After a few seconds, you should see

    Tunnel Status                 online
    Version                       1.7/1.7
    Forwarding                    https://adaptablehoney.oceanapp.io -> 127.0.0.1:8080
    Forwarding                    http://adaptablehoney.oceanapp.io -> 127.0.0.1:8080
    Web Interface                 127.0.0.1:4040
    # Conn                        0
    Avg Conn Time                 0.00ms

Now visit `http://adaptablehoney.oceanapp.io` on your computer to verify that the port is exposed.

## Other Features
You may run `surf --help` to get a list of all arguments and options:

    Usage: surf [OPTIONS] <local port or address>
    Options:
      -config="": Path to surf configuration file. (default: $HOME/.surf)
      -hostname="": Request a custom hostname from the surf server. (HTTP only) (requires CNAME of your DNS)
      -httpauth="": username:password HTTP basic auth creds protecting the public tunnel endpoint
      -log="none": Write log messages to this file. 'stdout' and 'none' have special meanings
      -log-level="DEBUG": The level of messages to log. One of: DEBUG, INFO, WARNING, ERROR
      -proto="http+https": The protocol of the traffic over the tunnel {'http', 'https', 'tcp'} (default: 'http+https')

    Examples:
        surf 80
        surf -proto=tcp 22


    Advanced usage: surf [OPTIONS] <command> [command args] [...]
    Commands:
        surf start [tunnel] [...]    Start tunnels by name from config file
        surf start-all               Start all tunnels defined in config file
        surf list                    List tunnel names from config file
        surf help                    Print help
        surf version                 Print surf version

    Examples:
        surf start www api blog pubsub
        surf -log=stdout -config=surf.yml start ssh
        surf start-all
        surf version

