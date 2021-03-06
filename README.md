# fsimchen Arch Linux Installer Script
# With BTRFS and Snapper, on a DOS/MBR disk partition

<img src="https://i.imgur.com/Yn29sze.png" />

This README contains the steps I do to install and configure a fully-functional Arch Linux installation containing a desktop environment, all the support packages (network, bluetooth, audio, printers, etc.), along with all my preferred applications and utilities. The shell scripts in this repo allow the entire process to be automated.)

---

## Setup Boot and Arch ISO on USB key

First, setup the boot USB and boot arch live iso. 

### Arch Live ISO

This step installs arch to your hard drive. *IT WILL FORMAT THE DISK*

You need to fork this git and edit the variables.sh file with your data for the scripts use.

When cfdisk open, select DOS, delete all partitions on the disk and create only one new, whole disk.

---

Step 1
```bash
loadkeys br-abnt2
```
```bash
pacman -Syy git
```
```bash
git clone https://github.com/fsimchen/arch
```
```bash
cd arch
```
```bash
sh 1_filesystem.sh
```
---
Step 2
```bash
arch-chroot /mnt
```
```bash
cd /opt/arch
```
```bash
sh 2_base.sh
```
```bash
exit
```
```bash
reboot
```
---
Step 3 (Log in as normal user)
```bash
loadkeys br-abnt2
```
```bash
cd /opt/arch
```
```bash
sh 3_install.sh
```
---
### Don't just run these scripts. Examine them. Customize them. Create your own versions.

---

### System Description
This runs Awesome Window Manager with the base configuration from the Material-Awesome project <https://github.com/fsimchen/material-awesome>.

---

#### No Wifi

```bash
sudo wifi-menu
```
