# Troubleshooting of problems with Ubuntu on ASUS ROG Flow x13 (GV302x)
-----------------------------------------------------------------------
xUbuntu 23.10 was used as the secondary system.
-----------------------------------------------------------------------
1. *Problem*: "System program problem detected" dialog is shown at each
              boot. Closing the dialog does not lead to solving the issue.
   
   *Solution*:
               Install NVIDIA proprietary driver.
               Blacklist NOUVEAU module:
               1.1 `sudo nano /etc/modprobe.d/blacklist-nouveau.conf`
                   Add the following:
                     `blacklist nouveau`
                     `options nouveau modeset=0`
               1.2 `sudo update-initramfs -u`
               1.3 `sudo rm /var/crash/*.crash`
               1.4 Reboot.
