# Raspberry-Pi-NAS-Setup

This GitHub project will help you with Raspberry Pi setup. 
I will talk about OpenMediaVaul and Samba. I will also show you some basic firewall setup.

**Used technologies.**
  - Raspberry Pi OS (Debian - based)
  - OpenMediaVault
  - Samba
  - NFS
  - UFW - firewall
  - ssh for remote access


1. **Setting up Raspberry**
   1. Download Raspberry Pi imager at *https://www.raspberrypi.com/software/*
   2. Run it and insert your microSD card into your computer.
   3. In Imager, select your Raspberry Pi model, the OS version (Raspberry Pi OS Lite 64-bit is recommended since only a terminal is needed), and your SD card as the boot device.
   4. Before you pressing install, press **Ctrl Shift X** and in window, **enable ssh** and customize your user *name and password.*
   5. After everything downloads,inser sd cart into Raspberry Pi, power it up and connect it into your network.
   6. In your router settings, you should see Raspberry Pi **IP adress.**
   7. In CMD write **ssh your_username@your_pi_ip_address**. Enter your password.
   8. Update your system packages **sudo apt update && sudo apt upgrade**.
   9. Your Raspberry Pi is now set up. The next step is configuring either OpenMediaVault or Samba for NAS to be fully functional. 

2. **Samba setup**
   1. In bash install your Samba - **sudo apt install samba nfs-kernel-server**
   2. Create your *share directory* - **sudo mkdir ~/nas_share**
   3. Edit Samba *configuration file* - **sudo nano /etc/samba/smb.conf**
       [nas_share]
         path = /home/"your_user"/shared
         read only = no
         browsable = yes
         valid users = @users
   4. Add a Samba user - **sudo smbpasswd -a "your_user"**
   5. Start and enable Samba service - **sudo systemctl restart smbd**, **- sudo systemctl enamble smbd**
   6. Now we can setup security measures.
  
3. **Security measures**
   1. **Install firewall** - **sudo apt install ufw**
   2. Allow Samba access within your home network - **sudo ufw all from "your_home_ip_network" to any port 445**
   3. Enable your **firewall** - **sudo afw enable**
   4. This setup will enable connection to Raspberry Pi inside your network, but now outside.


