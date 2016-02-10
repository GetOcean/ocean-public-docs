---
layout: page
title: Setup a simple web server on your Ocean
group: navigation
---

This is a very simple guide that will show you how to setup a simple static web server on your Ocean.

## Install `http-server`

We are first going to install a Node-JS application called `http-server`.  This application can be used to set up and run a simple static web server from any folder.  Install it with the following command:

    $ npm install -g http-server

You should see output like the following:

    $ npm install -g http-server
    /usr/local/bin/http-server -> /usr/local/lib/node_modules/http-server/bin/http-server
    /usr/local/bin/hs -> /usr/local/lib/node_modules/http-server/bin/http-server
    http-server@0.8.5 /usr/local/lib/node_modules/http-server
    ├── opener@1.4.1
    ├── corser@2.0.0
    ├── http-proxy@1.13.1 (eventemitter3@1.1.1, requires-port@1.0.0)
    ├── colors@1.0.3
    ├── optimist@0.6.1 (minimist@0.0.10, wordwrap@0.0.3)
    ├── union@0.4.4 (qs@2.3.3)
    ├── portfinder@0.4.0 (async@0.9.0, mkdirp@0.5.1)
    └── ecstatic@0.7.6 (url-join@0.0.1, mime@1.3.4, minimist@1.2.0, he@0.5.0)

## Create a simple HTML file and start a server

Next, create a separate folder somewhere with the following:

    $ mkdir simple-site && cd simple site

Then use the following command to create a very simple HTML file:

    $ echo "<h1>Hello World</h1>" > index.html

Finally, run `http-server`

    $ http-server

You should see output like the following:

    Starting up http-server, serving ./
    Available on:
      http:127.0.0.1:8080
      http:10.0.27.116:8080
    Hit CTRL-C to stop the server

That's it, now your web server is running!

## Visit the site in a browser

Enter the URL `http://10.0.27.116:8080` in a browser running on the same wireless network as your Ocean:

![]({{ site.baseurl }}/assets/images/HelloWorld.png)
