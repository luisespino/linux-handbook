[⬅ Back](../)

# Install Android Studio on Arch Linux

Upgrade the system:

```
sudo pacman -Syu
```

Install OpenJDK:
```
sudo pacman -S jdk-openjdk
```

Verify the JDK version:
```
java --version
```

You should see something like:
openjdk 24.0.1 2025-04-15

Then set the JDK version:
```
sudo archlinux-java set java-24-openjdk
```

Install yay (If you don't have yay yet):
```
sudo pacman -S --needed base-devel git
git clone https://aur.archlinux.org/yay.git
cd yay
makepkg -si
```

Alternatively, add chaotic-aur for easier AUR access: [https://github.com/chaotic-aur](https://github.com/chaotic-aur)

Then:
```
sudo pacman -S yay
```

Install Android Studio from AUR:
```
yay -S android-studio
```

Launch Android Studio, open it from your application menu or run:

![alt text](splash.png)

Follow the setup wizard:

- Select Standard Setup

- Accept the license agreement

- Finish the configuration

![alt text](start.png)


