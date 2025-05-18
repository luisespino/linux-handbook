[⬅ Back](../)

# Installing Go on Arch Linux

Update the system:
```
sudo pacman -Syu
```

Install Go:
```
sudo pacman -S go
```

Check the Go version:
```
go version
```

You should see a message like: go version go1.24.3 linux/amd64, or the current version.

Edit the .bashrc file:
```
nano ~/.bashrc
```

Add the following configuration:
```
export GOROOT=/usr/lib/go
export GOPATH=$HOME/go
export PATH=$PATH:$GOROOT/bin:$GOPATH/bin
```

Reload the shell:
```
source ~/.bashrc
```

Finally, restart the terminal.
