# Configure NFS Client on Raspberry Pi OS

Update the system:
```
sudo apt update
```

Install NFS client utilities:
```
sudo apt install nfs-common
```

Create the mount point (short paths are preferred):
```
mkdir ~/nfs
```

Finally, mount the shared directory (format: host:/server/fullpath /client/path):
```
sudo mount 192.168.1.19:/home/luisespino/nfs ~/nfs
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
192.168.1.19:/home/luisespino/nfs /mnt/nfs_client nfs defaults,_netdev 0 0
```

Reload systemd (optional but good practice):
```
systemctl daemon-reload
```

Test the fstab entry:
```
sudo mount -a
```

If everything works correctly, reboot:
```
sudo reboot now
```