# Raspberry-Pi-3 Setup

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
Pi Bake yourimages.
```
http://www.tweaking4all.com/hardware/raspberry-pi/macosx-apple-pi-baker/
```
How To Bake your Pi
```
https://www.maketecheasier.com/sd-card-images-raspberry-pi-mac/
```
