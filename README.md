# Groomsmen_Project

## Thank You
First off, I have to say a big thank you to you guys. Desite us not having known each other for very long in the grand scheme of things, I can say for certain that I was honored to have you stand with me up there on the aisle. It was a daunting day to say the least, but I couldn't ask for a better group of guys to be by my side. With the mushy stuff out of the way, lets get to the technical stuff.

## Base Configuration
This device is the Raspberry PI 3+ which includes a higher base clock at ~1.4 GHz and 1GB of RAM making it a suitable platform for a variety of tasks. Although the device could be used as another basic computer in your life, this device, in my personal opnion, can be best utilized as a basic home server serving a variety of services across the network. As such, this raspberry pi has been configured as such. It has three main OS images installed: [Raspbian Stretch Lite](https://www.raspberrypi.org/downloads/raspbian/), [Raspbian Stretch Full](https://www.raspberrypi.org/downloads/raspbian/), and [OSMC](https://osmc.tv/). Raspbian Stretch is based on Debian OS which makes it an extremely powerful fully fledged Linux machine. The only difference between the Lite and Desktop version is that the Lite is a minimal headless version to keep the overhead and the Desktop comes with a full GUI frontend. For this system, most if not all of the services have been installed on the Rasbian Stretch Lite images. Lastly, the OSMC acts as a convenient home media player that functions almost identically to a cracked Amazon Firestick. With everything said, feel free to change the setup to better suit your needs. Also, please remember to change the passwords once you've setup your device as these are very poor passwords.

## Projects
1. Media Center (OSMC / Kodi)
2. Retro Gaming Machine (Raspbian Lite)
3. OpenVPN Server (Raspbian Lite)
4. Miscellaneous

## NOOBS (Bootloader)
To make it convenient to install other builds, NOOBS v3.0 was installed as an initial boot loader. Currently, I went ahead and installed Raspbian Full (Desktop), Raspbian Lite, and OSMC Pi2 and each can be further customized if you want a full system, a low overhead server, or a dedicated entertainment system. 

## 1. OSMC
OSMC is a free and open source media center. 

### Login Details
Host Name: osmc-groomsmen

SSH Username: osmc

HTTP Webinterface Username: osmc

Password: groomsmen

Note: This password is used for both the Web Interface as well as the Apple Airplay password.

### Non-Standard Features Enabled:
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

# Raspbian Stetch Lite
This is essentially a low overhead version of the Raspbian project which is basically Debian OS.

### Login Details
Admin account: pi

Admin password: groomsmen

Username account w/ sudo: groomsmen

Password: groomsmen

### System Security
To make sure that you haven't added a vulnerable device to your system, [UnattendedUpgrades](https://wiki.debian.org/UnattendedUpgrades) was installed on your machine to perform automatic scheduled security patch installs everyday and reboots at 4:45 am if there were any packages installed. To implement these features, I followed this [post](https://blog.dantup.com/2016/04/setting-up-automatic-updates-on-raspberry-pi-raspbian-jessie/) with a few modifications to send the mail to the groomsmen user. To see what configurations were set, look at `/etc/apt/apt.conf.d/50unattended-upgrades`

## 2. Retropie:
Retropie is an amalmagation of console emulators that ranging from Nintendo 64 to Playstation 1. I did a basic install following the documentation found on their website [here](https://retropie.org.uk/docs/Manual-Installation/)

To start the RetroPie emulator, run `emulationstation` in the terminal, and it will bring up the main configuration menu. I made a basic configuration for the games: keypad is the directional keys, d is A, z is start, and x is select. I suggest you follow the insturctions here to reset the configuration to your liking. I haven't installed any ROMs on the system, but they can be found on the web with a simple search. It's technically illegal for me to distribute ROMs that I don't own the rights to.... so I'll just link you to some open source ones: https://pdroms.de/news/gameboy/

If you need to make adjustments to the configurations the home directory fot eh pi account contains the setup script.

### iPhone Controller 
If you're looking for a reto controller, an Iphone/Android device can be used instead of purchasing a controller. Here's a simple open source project that uses the web server on the raspbery pi to interact with your browser: https://github.com/retropie/retropie-setup/wiki/Virtual-Gamepad. Although it says it's Android only, it does seem to work as if configured correctly as stated [here](https://github.com/retropie/retropie-setup/wiki/Virtual-Gamepad).

## 3. OpenVPN Server
Not interested in paying $15 a month for a dedicated VPN host? Well you should take a look at how to setup a OpenVPN server on your raspberry pi: http://www.pivpn.io/ and https://medium.freecodecamp.org/running-your-own-openvpn-server-on-a-raspberry-pi-8b78043ccdea. Unfortunately, without access to your router, I cannot completely setup this service as it does require a bit of network configuration. However, if you are interested, let me know, and I can try to help you out.

There are three main parts to getting the server working:
1) Installing the OpenVPN daemon on your machine
2) Forwarding the correct port information on your router
3) Setting up a dynamic DNs forwarding service
  * There are [free services](https://www.noip.com/) that will direct DNS queries (e.g. groomsmen@dynamicDNS.net) to your home IP which is not a static.
  
If you do go down this path, realize that you are potentially exposing some of your network to the broad internet, but with proper setup, the risks are minimized.

## 4. Miscellaneous
Now it really comes down to your use case for this system, but below I included a few other project ideas / use cases that you can follow to get your system up and running. 
* [Quake Game Server](https://quake.ie/quake-on-lan/)
* [Wireless Print Server that supports Apple's AirPrint feature](https://opensource.com/article/18/3/print-server-raspberry-pi)
* [Network Monitor Tool](https://www.networkworld.com/article/2225683/cisco-subnet/cisco-subnet-raspberry-pi-as-a-network-monitoring-node.html)
* [Twitter Bot](https://www.instructables.com/id/Raspberry-Pi-Twitterbot/)

# Closing
As a final note, feel free to reach out to me if you guys run into any issues. This is the least I can do on my part as thanks for the time and energy that you have contributed to make my wedding and everything leading up to this point a special and memorable experience. You guys are the best.
