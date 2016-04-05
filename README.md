# Raspberry-Pi-3 Setup

#Starting with Noobs or Raspbian 

- [Raspberrypi.org/downloads](https://www.raspberrypi.org/downloads) 



Install updated packages:
```
sudo apt-get update
sudo apt-get updgrade -y
sudo apt-get dist-upgrade -y
```
Install Bluetooth packages:
```
sudo apt-get install pi-bluetooth
sudo apt-get install bluez bluez-firmware
sudo apt-get install blueman
sudo usermod -G bluetooth -a pi
```

Now reboot, to make sure everything is okay:
```
sudo shutdown -r now
```
Updates the kernel and firmware.
```
sudo rpi-update
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


#Additional Images 
  Gamming

- [RetroPi](https://github.com/RetroPie/RetroPie-Setup/wiki/First-Installation) 



#GPIO
![Alt Text](http://www.rpi-spy.co.uk/wp-content/uploads/2012/06/Raspberry-Pi-GPIO-Layout-Model-B-Plus-rotated-2700x900.png)

Power your Pi via GPIO via Pin #2 & #6
![Alt Text](http://www.modmypi.com/image/data/tutorials/how-to-power-my/4.png)


#Learn Python 
http://learnpython.org/
http://pi.cs.man.ac.uk/download/Raspberry_Pi_Education_Manual.pdf

#Minecraft and Programming on a Pi
Building A Castle In Minecraft With Python
http://www.raspberrypi-spy.co.uk/2014/06/building-a-castle-in-minecraft-with-python/

