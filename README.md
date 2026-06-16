## 🚀 How to Setup and Run Ubuntu 26 with XFCE Desktop

Follow these simple steps to install the app and set up your Linux desktop environment.

### Step 1: Install Termux
1. Download and install the `termux-app.apk` file included in this project folder.

### Step 2: Run the Setup Commands
Open Termux, copy the entire block of commands below, paste it into Termux, and press **Enter**:

```bash
# Allow Termux to read your files
termux-setup-storage

# Go to your extracted GitHub project folder (Change 'your-folder-name' to match your zip file)
cd /sdcard/Download/your-folder-name

# Update Termux packages and install PRoot
pkg update -y && pkg install proot -y

# Create a folder for Ubuntu and extract the system file
mkdir -p ~/ubuntu26
tar -xvf ubuntu-rootfs.tar.gz -C ~/ubuntu26

# Log into Ubuntu and automatically install the lightest XFCE desktop
proot -r ~/ubuntu26 -0 -w /root /bin/bash -c "
  apt update && apt upgrade -y
  apt install --no-install-recommends xfce4 xorg tightvncserver -y
  echo 'Installation complete! You can now start the desktop.'
"
