# TigerVNC Client Connect

Update the system:
```
sudo pacman -Syu
```

Install yay (if you don't have it yet), as TigerVNC Viewer is in the AUR:
```
sudo pacman -S yay
```

Install TigerVNC Client:
```
yay -S tigervnc-viewer
```

To connect, execute vncviewer with IP and port:
```
vncviewer 192.168.1.24:5901
```

If you're using i3WM, set fullscreen to accept the "Win" key:
- Press F8, then select Fullscreen.
