---
layout: page
title: Installing 'surf' on Your Ocean
group: navigation
---

`surf` is a script to setup tunneling localhost so you can easily expose any localhost ports to the world. You will receive a URL `someName.oceanapp.io` that can easily expose any port running on your Ocean. `surf` is signed with our certification and a unique authentication token to for a secure connection. You need to first acquire a token, then sign the script with it. 

## Installing

To get started, please first visit the [Dashboard](https://app.getocean.io) and login with your username/password. Once logged in, you will see a list of your Oceans:

![Dashboard]({{ site.baseurl }}/assets/images/SetupTunnel.png)

By default, the name is chosen as the name of your Ocean. You may change the name if you wish to. 

After confirming the URL, you will be presented with the command to make `surf`. Treat the `authToken` just as you would treat any other password:

    sudo apt-get install golang mercurial -y && \ 
    wget https://s3-us-west-1.amazonaws.com/get-ocean/surf.tar.gz && \ 
    tar -zxvf surf.tar.gz && \ 
    cd surf && \ 
    make authToken=aUniqueToken123 domain=capableedge 

Verify installation was successful by entering `which surf`. You should see:

    /usr/local/bin/surf

## Using
Please visit [this]({{ sites.baseurl }}/using-surf) guide to learn on how to use `surf`. 