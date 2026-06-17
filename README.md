## 🚀 How to Setup and Run Ubuntu 26 with XFCE Desktop

Follow these simple steps to install the app and set up your Linux desktop environment.

### Step 1: Install Termux
1. Download and install the `termux-app.apk` file included in this project folder.

### Step 2: Run the Setup Commands
Open Termux, copy the entire block of commands below, paste it into Termux, and press **Enter**:

```bash
pkg update

```
```bash
pkg upgrade-y
```
```bash
pkg install proot-distro -y
```
```bash
proot-distro install ubuntu
```
```bash
proot-distro login ubuntu
```
```bash
apt update && apt upgrade -y
apt install xfce4 xfce4-goodies tigervnc-standalone-server nano -y
```
type the passward and type again and you can,t see the passward
```bash
vncpasswd
```
```bash
mkdir -p ~/.vnc
```
```bash
nano ~/.vnc/xstartup
```
copy the code  annd past and then prss ctrl+o and ctrl+x
```bash
#!/bin/sh
unset SESSION_MANAGER
unset DBUS_SESSION_BUS_ADDRESS
startxfce4 &
```
```bash
chmod +x ~/.vnc/xstartup
```
```bash
vncserver -geometry 1280x720 :1
```



