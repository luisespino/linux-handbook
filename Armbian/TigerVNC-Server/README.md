[⬅ Back](../)

# TigerVNC Server Setup

Update the system:
```
sudo apt update
```

Install TigerVNC Server and Tools:
```
sudo apt install tigervnc-standalone-server tigervnc-common tigervnc-tools -y
```

Set the VNC password:
```
vncpasswd
```

When prompted:
- Would you like to enter a view-only password (y/n)? → type n

Create the configuration directory:
```
mkdir -p ~/.vnc
```

Configure directory permissions:
```
chmod -R 700 ~/.vnc
chown -R luisespino:luisespino ~/.vnc
```

Edit the xstartup file:
```
nano ~/.vnc/xstartup
```
Configure it as follows:

[~/.vnc/xstartup](TigerVNC-Server.xstartup)

Make sure it starts your preferred window manager (e.g., i3, xfce4-session, etc.).


Make xstartup executable:
```
chmod +x ~/.vnc/xstartup
```
Edit the systemd service file:
```
sudo nano /etc/systemd/system/vncserver@.service
```

Configure it as follows:

[/etc/systemd/system/vncserver@.service](TigerVNC-Server.service)


Reload and enable the service:
```
sudo systemctl daemon-reload
sudo systemctl enable vncserver@1.service
```

Finally, restart the system:
```
sudo reboot now
```

## Additional Commands

You can manage the VNC server using the following (individually):
```
sudo systemctl status vncserver@1.service
vncserver -kill :1
sudo systemctl stop vncserver@1.service
sudo systemctl disable vncserver@1.service
```

If the service file doesn't work properly, you can manually start the VNC server:
```
/usr/bin/vncserver :1 -geometry 1280x1024 -depth 24 -localhost no
```

If everything is working, you’ll see a message like:

<pre>New Xtigervnc server 'nezha:1 (luisespino)' on port 5901 for display :1.
Use xtigervncviewer -SecurityTypes VncAuth,TLSVnc -passwd /home/luisespino/.vnc/passwd nezha:1 to connect to the VNC server.
sr/bin/vncserver :1 -geometry 1280x1024 -depth 24 -localhost no</pre>


