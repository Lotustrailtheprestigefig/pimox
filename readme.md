Pimox - Proxmox V7 for the Raspberry Pi
Pimox is a port of Proxmox to the Raspberry Pi allowing you to build a Proxmox cluster of Rapberry Pi's or even a hybrid cluster of Pis and x86 hardware.

Requirements
Raspberry Pi 4
Internet connection via ethernet
Install from "scratch", RPiOS64bit Interactive Automatic Installer
Flash and startup the latest image from https://downloads.raspberrypi.org/raspios_arm64/ .
sudo -s
curl https://raw.githubusercontent.com/pimox/pimox7/master/RPiOS64-IA-Install.sh > RPiOS64-IA-Install.sh
chmod +x RPiOS64-IA-Install.sh
./RPiOS64-IA-Install.sh
Follow the prompts
Manual installation
Prechecks

Pre-installed Debian Bullseye based 64-bit OS (not 32bit)
In /etc/network/interfaces, give the Pi a static IP address. You cannot use dhcp.
In /etc/network/interfaces, remove any IPv6 addresses.
In /etc/hostname, make sure the Pi has a name.
In /etc/hosts, make sure this hostname corresponds to the static IP you previous set.
Make sure the kernel-headers are installed.
Installation

echo "deb https://raw.githubusercontent.com/pimox/pimox7/master/ dev/" > /etc/apt/sources.list.d/pimox.list
curl https://raw.githubusercontent.com/pimox/pimox7/master/KEY.gpg | apt-key add -
apt update
apt install proxmox-ve (use a local attatched console! Network connections will be lost/reset during installation progress)
Notes
This repo just contains the precompiled debian packages. The original Proxmox sources can be found at https://git.proxmox.com
The (very minimally) patched sources to rebuild this can be found at https://github.com/pimox