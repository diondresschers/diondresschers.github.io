<img src="../static/amsterdam_umc_logo_rgb.svg" height="50%" width="50%" style="display: block; margin-left: auto;
 margin-right: auto; width: 50%;">
<p style="text-align:center; font-size: 200%;">Apotheek</p>
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/fork-awesome@1.1.7/css/fork-awesome.min.css" integrity="sha256-gsmEoJAws/Kd3CjuOQzLie5Q3yshhvmo7YNtBG7aaEY=" crossorigin="anonymous">

* License: <i class="fa fa-creative-commons" aria-hidden="true"></i> CC BY-SA 4.0
* By: Dion Dresschers of Amsterdam UMC
* Version: 2020-03-20 12:09:49

# Ubuntu 18.04 on Raspberry Pi 4 Cheat Sheet

## Download Raspberry Pi Imager

[Raspberry Pi Downloads - Software for the Raspberry Pi](https://www.raspberrypi.org/downloads/)

## Download Ubuntu 18.04 64-bit

[Thank you for downloading Ubuntu Server for Raspberry Pi | Ubuntu](https://ubuntu.com/download/raspberry-pi/thank-you?version=18.04.4&architecture=arm64+raspi3)

# sound

```
apt install pi-bluetooth # on ubuntu 19.10 server
```

# startup files

```
vi /boot/firmware/config.txt
vi /boot/firmware/sysconfig.txt
vi /boot/firmware/usrconfig.txt
vi /boot/firmware/btcfg.txt
vi /boot/firmware/nobtcfg.txt
```