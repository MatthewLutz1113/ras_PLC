- [Raspberry Pi PLC Project.](#raspberry-pi-plc-project)
  - [Setup Raspberry Pi](#setup-raspberry-pi)
  - [Install OpenPLC Runtime on Raspberry Pi](#install-openplc-runtime-on-raspberry-pi)
  - [Install HomeBridge GPIO Plugin on Teensy](#install-homebridge-gpio-plugin-on-teensy)


# Raspberry Pi PLC Project.

The goal of this project is to use a Raspberry Pi

Uses a Raspberry Pi as a PLC, with OpenPLC (CODESYS?). Input commands are from sensors as well as HomeKit commands input using the HomeBridge Module. 

## Setup Raspberry Pi

Erase disk to MS-DOS (FAT).

Use Raspberry Pi imager to flash full desktop

## Install OpenPLC Runtime on Raspberry Pi

`yadda`

## Install HomeBridge GPIO Plugin on Teensy

https://github.com/tnys/homebridge-gpio

```git clone git://github.com/jamesblanksby/quick2wire-gpio-admin.git \n
cd quick2wire-gpio-admin
make
sudo make install
sudo adduser $USER gpio
```

Yay
