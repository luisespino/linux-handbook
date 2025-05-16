[⬅ Back](../)

# i3WM Setup

Update and upgrade the system:
```
sudo apt update && sudo apt upgrade -y
```
Install XORG Server, Protocol and Utilities:
```
sudo apt install xorg xserver-xorg x11-xserver-utils -y
```
Instal i3Wm and LightDM:
```
sudo apt install i3 lightdm lightdm-greeter-gtk -y
```

Install additional packages (optional):
```
sudo apt install lxterminal polybar epiphany-browser epiphany-browser -y
```

Set LightDM as the default session manager:
```
sudo dpkg-reconfigure lightdm
```

Finally, restart the system:
```
sudo reboot now
```