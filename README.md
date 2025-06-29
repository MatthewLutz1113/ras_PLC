# Sliding Door Control
Uses a Raspberry Pi as a PLC, with OpenPLC, to control sliding door blinds movement and rotation. Input commands are from sensors as well as HomeKit commands input using the HomeBridge Module. 

## Install OpenPLC Runtime on Raspberry Pi

`yadda`

## Install HomeBridge GPIO Plugin

https://github.com/tnys/homebridge-gpio

`git clone git://github.com/jamesblanksby/quick2wire-gpio-admin.git
cd quick2wire-gpio-admin
make
sudo make install
sudo adduser $USER gpio`
