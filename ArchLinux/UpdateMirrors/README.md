[⬅ Back](../)

# Update Mirrors on Arch Linux

To get the fastest mirrors, install the Reflector package:
```
sudo pacman -S reflector
```

Make a backup of the current mirror list:
```
sudo cp /etc/pacman.d/mirrorlist /etc/pacman.d/mirrorlist.backup
```

Use Reflector to get the 20 fastest HTTPS mirrors in your preferred country, and save them to the mirror list:
```
sudo reflector --country "United States" --protocol https --latest 30 --fastest 20 --sort rate --download-timeout 10 --threads 10 --save /etc/pacman.d/mirrorlist
```

Finally, update the mirror list and upgrade the system:
```
sudo pacman -Syyu
```
