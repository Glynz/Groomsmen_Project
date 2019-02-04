# Groomsmen_Project

## Thank You
First off, I have to say a big thank you to you guys. Desite us not having known each other for very long in the grand scheme of things, I can say for certain that I was honored to have you stand with me up there on the aisle. It was a daunting day to say the least, but I couldn't ask for a better group of guys to be by my side. With the mushy stuff out of the way, lets get to the technical stuff.

## Base Configuration
This device is the Raspberry PI 3+ which includes a higher base clock at ~1.4 GHz and 1GB of RAM making it a suitable platform for a variety of tasks. Although the device could be used as another basic computer in your life, this device, in my personally opnion, can be best utilized as a basic home server serving a variety of services across the network. As such, this raspberry pi has been configured as such. It runs using the [Raspbian Stretch Lite package](https://www.raspberrypi.org/downloads/raspbian/) which is a minimal headless version to keep the overhead low. With everything said, feel free to change this as it suits your needs.

## Projects
1. Media Center (OSMC / Kodi)
2. Retro Gaming Machine
3. Network Monitoring Tool
4. OpenVPN Server

## NOOBS (Bootloader)
To make it convenient to install other builds, NOOBS v3.0 was installed as an initial boot loader. Currently, I went ahead and installed Raspbian Full (Desktop), Raspbian Lite, and OSMC Pi2 and each can be further customized if you want a full system, a low overhead server, or a dedicated entertainment system. 

## OSMC
OSMC is a free and open source media center. 

###Login Details
Host Name: osmc-groomsmen
SSH Username: osmc
HTTP Webinterface Username: osmc
Password: groomsmen
Note: This password is used for both the Web Interface as well as the Apple Airplay password.

###Non-Standard Features Enabled:
1) Remote Control via HTTP
  - This allows for your phone/pc to be used as a remote for the system
  - required username and password
2) Apple Airplay Support
  - You can just share media from your Apple device to the server and it will play
3) Automatic Updates
4) Enabled the event logger
5) Enabled third party app installation

### Video Addons:
Installed a variety of Video Addons such as Youtube, Twitch, Southpark, etc. from the main OSMC repository, and I also installed Netflix and Amazon Prime from third party developers (https://makingstuffwork.net/technology/install-netflix-amazon-prime-video-plex-raspberry-pi-kodi-osmc/). The zip files for the addons can be found in the home directory. Before you can use the latter video addons, you'll need to use your personal credentials to sign into the app--sorry boys, no free accounts. For those interested in installing Hulu, follow the instructions listed here: https://thevpn.guru/hulu-kodi-addon-xbmc-install-vpn/.

### Remote Control Setup:
There's probably a better remote control app, but I found the officially supported app to work on both Apple and Android devices: http://cagewebdev.com/raspberry-pi-using-your-android-phone-as-a-remote-control-for-raspbmc/. Bassically install the app from your respective app store and download it. Next, open the device and add a new host. There should be a button to simply find any OSMC devices on your wifi network. Once found, put in the above username and password and voila! You'll be able to use your phone/device as a remote control for the OSMC.

### Accessing the command line:
https://osmc.tv/wiki/general/accessing-the-command-line/

### Miscellaneous:
OSMC can also be configured to stream less than legal content onto the device similarly to Amazon's firestick hack. I did not install the apps necessary for this functionality, but if you're interested, all the configurations are properly setup. That moral choice is up to you now but know the risks invovled.
