[⬅ Back](../)

# Update Mirrors on Arch Linux

This mirror update process can be repeated depending on how often you update the system; it could be every week or whenever the download speed is slow.

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
sudo reflector --country "United States" --protocol https --latest 50 --fastest 20 --sort rate --threads 10 --save /etc/pacman.d/mirrorlist
```

Finally, update the mirror list and upgrade the system:
```
sudo pacman -Syyu
```
