# Raspberry-Pi-3 Setup

#Starting with Noobs or Raspbian 

- [Raspberrypi.org/downloads](https://www.raspberrypi.org/downloads) 



Install updated packages:
```
sudo apt-get update
sudo apt-get upgrade -y
sudo apt-get dist-upgrade -y
```

Now reboot, to make sure everything is okay

```
sudo shutdown -r now
```

Raspberry Pi configuration tool 
```
sudo raspi-config
```
1 Expand Filesystem 

2 Enable Camera (if needed)

df command  – to check free disk space

```
df -h
```

Updates the kernel and firmware.
```
sudo rpi-update
```
1 Expand Filesystem 
2 Enable Camera (if needed)
3 Change your Pi Hostname. (if you want)


# General Commands
```
apt-get update: Updates your version of Raspbian.
apt-get upgrade: Upgrades all of the software packages you have installed.
clear: Clears the terminal screen of previously run commands and text.
date: Prints the current date.
find / -name example.txt: Searches the whole system for the file example.txt and outputs a list of all directories that contain the file.
nano example.txt: Opens the file example.txt in “Nano”, the Linux text editor.
poweroff: To shutdown immediately.
raspi-config: Opens the configuration settings menu.
reboot: To reboot immediately.
shutdown -h now: To shutdown immediately.
shutdown -h 01:22: To shutdown at 1:22 AM.
startx: Opens the GUI (Graphical User Interface)
```



#Pi Bake yourimages.
```
http://www.tweaking4all.com/hardware/raspberry-pi/macosx-apple-pi-baker/
```
#How To Bake your Pi
```
https://www.maketecheasier.com/sd-card-images-raspberry-pi-mac/
```
https://github.com/RetroPie/RetroPie-Setup/wiki/First-Installation

#Find your Pi using Nmap 
sudo nmap -sP 192.168.1.0/24 
look for (Raspberry Pi Foundation)

#Additional Images 
  Gamming

- [RetroPi](https://github.com/RetroPie/RetroPie-Setup/wiki/First-Installation) 



#GPIO
![Alt Text](http://www.rpi-spy.co.uk/wp-content/uploads/2012/06/Raspberry-Pi-GPIO-Layout-Model-B-Plus-rotated-2700x900.png)

Power your Pi via GPIO via Pin #2 & #6
![Alt Text](http://www.modmypi.com/image/data/tutorials/how-to-power-my/4.png)



#Use the Mac’s Finder to mount the Pi’s volume:
Install Netatalk, using the Pi’s Terminal command (a one-time setup):
```
sudo apt-get install netatalk
```
From the Mac Finder’s ‘Go’ menu, select ‘Connect to Server…’
Enter the Server Address, e.g.: afp://192.168.0.15
Click the ‘Connect’ button.
Enter your Pi’s username and password

Raspberry Pinouts and Pi HATs, pHATs & Add-ons Connections 
```
http://pinout.xyz/boards
```

Resistor calculator
```
http://resistor.cherryjourney.pt
```



#Learn Python 
http://learnpython.org/
http://pi.cs.man.ac.uk/download/Raspberry_Pi_Education_Manual.pdf

#Minecraft and Programming on a Pi
Building A Castle In Minecraft With Python
http://www.raspberrypi-spy.co.uk/2014/06/building-a-castle-in-minecraft-with-python/

#PiTFT Setup 
The following setup sequence requires RetroPie (3.6 or later) or Raspbian Jessie or Jessie Lite (2016-03-18 or later). “Native” PiTFT support like this is a very recent addition, and all models of Raspberry Pi (including the Pi 3) are supported.
```
sudo apt-get update
sudo apt-get install cmake git
git clone https://github.com/tasanakorn/rpi-fbcp
cd rpi-fbcp/
mkdir build
cd build/
cmake ..
make
sudo install fbcp /usr/local/bin/fbcp
```
Then we’ll edit one file to launch fbcp automatically as the system boots (feel free to substitute your editor of preference in place of “nano”):
```
sudo nano /etc/rc.local
```
Before, the final “exit 0” line, insert the following:
```
/usr/local/bin/fbcp &
```
Save the changes and exit.
We won’t be seeing the console much, but for those rare occasions, let’s set it up for a font better suited to the small PiTFT display:
```
sudo dpkg-reconfigure console-setup
```
Select “UTF-8”
“Guess optimal character set” 
“Terminus” and “6x12 (framebuffer only).”

Edit the file /boot/config.txt

add the following four lines. Most of these (all but the hdmi_cvt line) may already be present in the file, but may have different values and/or are commented out (with a “#” character at the start of the line). You can either delete those lines, or leave them commented out, replacing them with the new lines we provide here:

```
hdmi_force_hotplug=1
hdmi_group=2
hdmi_mode=87
hdmi_cvt=320 240 60 1 0 0 0
```

The four “hdmi” lines set the HDMI output to 320x240 pixels, to exactly match the PiTFT resolution.
Then, to enable the PiTFT device, add one of the following two lines…either:

```
dtoverlay=pitft28-resistive-overlay,rotate=90,speed=80000000,fps=60
or:
dtoverlay=pitft28-capacitive-overlay,rotate=90,speed=80000000,fps=60
```

…depending whether you have the resistive or capacitive PiTFT screen. For a 2.2" PiTFT, either one works since that screen doesn’t support touch.
Though the Pi has no trouble generating 320x240 video, not all HDMI monitors can display this. You might see “no signal” on the monitor following the next reboot. That’s okay…with everything set up right, it’ll all be routed to the PiTFT after a few seconds’ boot time.
Let’s give it a try…save the changes and reboot.

On startup, after a few seconds’ delay, you should see the RetroPie splash screen on the PiTFT, followed by the rest of the boot process and then EmulationStation. Go ahead and try launching something!
If an HDMI monitor is still attached, and if it supports 320x240 resolution, you should see the same content on both the monitor and PiTFT.
Once the system is working satisfactoraly, you can disconnect the HDMI monitor. Everything’s now done through the PiTFT (or remote login via SSH).

#Remapping Controls
```
cd Adafruit-Retrogame
sudo nano retrogame.c
make retrogame
sudo mv retrogame /usr/local/bin
sudo reboot
```

