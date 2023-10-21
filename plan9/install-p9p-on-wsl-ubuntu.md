# Installing plan9port on ubuntu in WSL

To install https://github.com/9fans/plan9port clone it and

```
sudo apt install libx11-dev libxt-dev libfontconfig-dev libxcomposite-dev 
```

go to the checkout and `./INSTALL`

I use these extra fonts:

```
sudo apt install fonts-firacode
```

I use https://sourceforge.net/projects/vcxsrv/files/vcxsrv/ as the windows X11. I do not use the wayland server `wslg` that comes with WSL2.

I put a `.wslconfig` in my Windows user home folder:

```
[wsl2]
memory=12GB
swap=0
localhostForwarding=true
guiApplications=false
```

I use

```
export DISPLAY=$(ip route | grep default | awk '{print $3; exit;}'):0.0
```

to tell X11 apps where to find the display server.

