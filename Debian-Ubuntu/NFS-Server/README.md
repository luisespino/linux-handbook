[⬅ Back](../)

# Configure NFS Server on Debian/Ubuntu

Update the system:
```
sudo apt update
```

Install NFS Server:
```
sudo apt install nfs-kernel-server
```

Start the NFS service permanently:
```
sudo systemctl start nfs-kernel-server.service
```

Create the desired directory:
```
mkdir ~/nfs
```

Set permission if you want full access:
```
sudo chmod 777 ~/nfs
```

Assign nobody:nogroup to the directory:
```
sudo chown -R nobody:nogroup ~/nfs
```

Edit the exports file:
```
sudo nano /etc/exports
```

Add a line to share the directory in the exports file:
```
~/nfs *(rw,sync,no_subtree_check)
```

Update the exportfs:
```
sudo exportfs -a
```

Restart the NFS service:
```
sudo systemctl restart nfs-kernel-server
```

Finally, check the shared directory using exportfs:
```
sudo exportfs -v
```