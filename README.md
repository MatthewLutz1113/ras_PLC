- [Raspberry Pi PLC Project using a Mac and a Raspberry Pi 4](#raspberry-pi-plc-project-using-a-mac-and-a-raspberry-pi-4)
- [Install and Setup](#install-and-setup)
  - [Raspberry Pi](#raspberry-pi)
  - [OpenPLC Runtime](#openplc-runtime)
  - [OpenPLC IDE](#openplc-ide)
    - [...on Raspberry Pi](#on-raspberry-pi)
    - [...on Mac](#on-mac)
- [Hello World!](#hello-world)


# Raspberry Pi PLC Project using a Mac and a Raspberry Pi 4

The goal of this project is to use a Raspberry Pi as an at-home PLC. Why? 
Firstly, there is a large community of PLC hobbyists who use Raspberry Pi's as PLCs.
In addition, Raspberry Pi's are extremely cheap, compared to industrial or practice PLCs, which can range from hundreds to thousands of dollars --not including software.

There are a few options out there to turn Raspberry Pi's into PLCs.
The first uses the CODESYS library, and follows IEEE standards.
CODESYS is used in a variety of industrial PLCs  ([Wago, AutomationDirect, Eaton, Wago, etc.](https://us.codesys.com/ecosystem/discover-codesys/codesys-inside/)).
The CODESYS IDE runs exclusively on Windows, so this option is ruled out for me.

Since I do not have access to a Windows computer (... silly me), I will be using OpenPLC Runtime to turn my Raspberry Pi into a PLC.
The advantage of OpenPLC compared to CODESYS for Raspberry Pi is that the programming IDE is web-based, meaning that I can program the PLC from my Mac.
In addition, while CODESYS is a paid platform, OpenPLC is completely free and open-source.
The disadvantage is that OpenPLC Runtime is not built to a widespread standard like CODESYS; however, OpenPLC is still a helpful tool to learn the basics of ladder logic and PLC I/Os.

# Install and Setup

The following setup is how I got OpenPLC Runtime to turn my Raspberry Pi into a PLC!

## Raspberry Pi

Here are the following steps to start with a fresh Raspberry Pi, which includes the desktop.
This requires the [Raspberry Pi Imager](https://www.raspberrypi.com/software/), which guides 

* Erase disk to MS-DOS (FAT).
* Use Raspberry Pi Imager to flash the Raspberry Pi OS (64-bit)
  * During this step, enter LAN credentials and allow SSH in the settings.

The imager will guide you through the flashing and checking process. When this is complete, plut the MicroSD back into the Raspberry Pi and power on your Pi. 

## OpenPLC Runtime

SSH into your Raspberry Pi from your home device.
This is not required, but I think it is helpful.
Do this by:

```
(base) user@Mac ~ % ssh your_username@<IP-address>
```

We will follow the helpful instructions in [this page](https://openplcproject.github.io/runtime/raspberry-pi/) to install OpenPLC on Rasberry Pi.

First, install or update git.

```
sudo apt-get install git
```

Then, install [OpenPLC_v3](https://github.com/thiagoralves/OpenPLC_v3) using git.

```
git clone https://github.com/thiagoralves/OpenPLC_v3.git
cd OpenPLC_v3
./install.sh rpi
```

This install is fairly hefty, and I can confirm that it takes a while.
After the install is complete and the Raspberry Pi reboots, the OpenPLC web server can be accessed through the Raspberry Pi IP address and :8080.

This is as simple as typing 

```
<your_IP_address>:8080
```

Into the web browser of a machine on the same Wifi. 
Enter the default credentials for the web server username: "OpenPLC", pw: "OpenPLC", and change these credentials in the "Users" tab of the web browser .


Then, enter the "Hardware" tab of the web browswer GUI and change the Open PLC hardware layer to "Raspberry Pi".

## OpenPLC IDE

### ...on Raspberry Pi

To enter the OpenPLC editor, where projects can be developed using ladder logic, one then needs to run the following on the Raspberry Pi:

```
sudo apt-get install git
git clone https://github.com/thiagoralves/OpenPLC_Editor
cd OpenPLC_Editor
./install.sh
```

**Raspberry Pi Virtual Window**

To access the editor on Raspberry Pi from my Mac, I installed [RealVNC](https://manage.realvnc.com/en/download/v8/connect?lai_vid=eebW6M2dkFaV&lai_sr=10-14&lai_sl=l&ts=a). This way I can pull up a virtual window into my Raspberry Pi to access the IDE.

To enable VNC on the Pi, enter
`
sudo raspi-config
`
and enable VNC under the "Interface Options" tab.

### ...on Mac

Follow the directions [here](https://autonomylogic.com/download).

# Hello World!

We will hello world the Raspberry PiLC with a basic [ladder logic programming example](https://autonomylogic.com/docs/3-2-creating-your-first-project-on-openplc-editor/).


<!-- ## Install HomeBridge GPIO Plugin on Teensy

https://github.com/tnys/homebridge-gpio

```git clone git://github.com/jamesblanksby/quick2wire-gpio-admin.git \n
cd quick2wire-gpio-admin
make
sudo make install
sudo adduser $USER gpio
``` -->

