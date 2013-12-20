---
layout: post
title: "Pi in the Sky"
date: 2013-12-05 11:07:48 -0800
comments: true
categories: RyBot
excerpt: "Hardware setup for our beloved microprocessor."
sharing: true
---
##Raspberry Pi Model B Edition
<!--more-->
{% img roundrect /images/20131204_153106.jpg 640 400 %}

{% pullquote %}
Beginning with the Raspberry Pi Model B, I've {"added 3 aluminum heat sinks to keep our baby cool while overclocked"}. These can be found on Amazon for around 5 bucks.


>I've found that a medium overclock works best for performance. Higher overclock settings often result in the dreaded *kdb prompt*.
{% endpullquote %}

**This blog is very helpful for optimizing performance. =>  [Raspbian Tuning](https://extremeshok.com/2012/07/22/raspberry-pi-raspbian-tuning-optimising-optimizing-for-reduced-memory-usage/)**

#Clear case with breadboard


{% img roundrect /images/20131204_153433.jpg 640 400 %}

{% pullquote %}
I've encased my pi in a clear case with openings for the ribbon cable, card slot, and power source. {"Because I'd like to keep soldering to a minimum for this prototype, I have attached a mini breadboard to the top of the case."} We're sure to have quite a spaghetti junction of wires going on here, but man, I just hate soldering. 
{% endpullquote %}

The cable attached is a USB to TTL Serial connector which you can find on [Adafruit](http://www.adafruit.com/products/954). I use this for initial setup, and getting the wifi settings loaded up. It's also incredibly useful for troubleshooting when you are unable to ssh into the board.

*The command you'll run from your terminal to connect over TTL will look like this:*

``` bash TTL over USB
screen /dev/cu.PL2303-00002014 115200
```


# GPIO Breakout
{% img roundrect /images/20131206_154137.jpg 640 400 %}

Since we're going to be breadboard protyping, we need access to those GPIO (General Purpose In/Out) pins.

[Here's](https://www.adafruit.com/products/914) one that Adafruit offers.

Oh, and that jobby sticking out of the USB port is a wireless adapter. Just about any usb adapter will do. Just set your /etc/network/interfaces file to look like this.

``` bash Interface Configuration
auto lo

iface lo inet loopback
iface eth0 inet dhcp

auto wlan0
allow-hotplug wlan0
iface wlan0 inet dhcp
      wpa-ssid "My-Network-SSID"
      wpa-psk "MY-Wifi-Password"
```
<div class="right">
  <a class="btn btn-success" href="http://rybot.org/blog/2013/12/06/rybot-peripherals/">Peripherals >></a>
</div>
