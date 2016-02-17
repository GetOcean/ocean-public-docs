---
layout: page
title: Ocean Documentation
group: navigation
---

Welcome to the Ocean documentation website!  This site contains a growing collection of guides and tutorials for setting up your Ocean and getting the most out of it.

# Getting Started

{% include intro/getting-started.md %}


# Guides and Tutorials

### Setup a Static Web Server

It's very easy to set up a web server on your Ocean that can serve static HTML files.  This guide explains how to do it.

- [Set up a static web server on your Ocean]({{ site.baseurl }}/setup-simple-webserver)


### Add Another WiFi Network

A wifi setup tool is already installed by default on all Oceans.

- [Use `wifi-setup` to Add Another WiFi Network]({{ site.baseurl }}/wifi-setup-tool)

You can also add WiFi networks manually by editing the `wpa_supplicant` config files.

- [Add Another WiFi Network with `wpa_supplicant`]({{ site.baseurl }}/wifi-wpa-supplicant)


# Troubleshooting

### Fix Filesystem Errors with `fsck`

Most Linux distributions have a utility called `fsck` that can automatically fix many filesystem problems.  This section explains how to run `fsck` on your Ocean.

- [Fix filesystem errors with fsck]({{ site.baseurl}}/fsck-disk)


# Working on Ocean

### Open Source

Our source code repositories are [available on github here](https://github.com/GetOcean).

### About the Ocean OS

All Oceans come pre-installed with a customized version of [Debian Jessie](https://www.debian.org/releases/stable/), using version 3.4.105 of the Linux kernel.

- [About the kernel and pre-installed packages]({{ site.baseurl}}/ocean-os)
