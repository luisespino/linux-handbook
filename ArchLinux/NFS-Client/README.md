[⬅ Back](../)

# Configure NFS Client on Raspberry Pi OS

Update the system:
```
sudo pacman -Syu
```

Install NFS client utilities:
```
sudo pacman -S nfs-utils
```

Create the mount point (short paths are preferred):
```
mkdir ~/nfs
```

Finally, mount the shared directory (format: host:/server/fullpath /client/path):
```
sudo mount 192.168.1.21:/home/luisespino/nfs ~/nfs
```

To unmount the shared directory:
```
sudo umount ~/nfs
```

To mount the shared directory permanently, edit the fstab file:
```
sudo nano /etc/fstab
```

Add the following line (format: host:/server/path /client/path nfs options dump pass):
```
192.168.1.19:/home/luisespino/nfs /home/luisespino/nfs nfs defaults,_netdev 0 0
```

Enable the NFS Client Service:
```
sudo systemctl enable --now nfs-client.target
```

Test the fstab entry:
```
sudo mount -a
```

If everything works correctly, reboot:
```
sudo reboot now
```