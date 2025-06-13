[⬅ Back](../)

# Configure NFS Server on ArchLinux

Update the system:
```
sudo pacman -Syu
```

Install NFS Utilities:
```
sudo pacman -S nfs-utils
```

Enable and start the NFS service permanently:
```
sudo systemctl enable nfs-server.service
sudo systemctl start nfs-server.service
```

If an error occurs while starting the service, try installing the linux and linux-headers packages to ensure they match your current kernel version and that the NFS module can be loaded:
```
sudo pacman -S linux linux-headers
```

Sometimes it is necessary to reboot the system. Try starting the NFS server service again.

Check the status of the NFS service — it should be active:
```
sudo systemctl status nfs-server
```

Create the desired directory:
```
mkdir ~/nfs
```

Set permission if you want full access:
```
sudo chmod 777 ~/nfs
```

Edit the exports file:
```
sudo nano /etc/exports
```

Add a line to share the directory in the exports file:
```
/home/luisespino/nfs *(rw,sync,no_subtree_check)
```


Restart the NFS service:
```
sudo systemctl restart nfs-server
```

Finally, check the shared directory using exportfs:
```
sudo exportfs -v
```