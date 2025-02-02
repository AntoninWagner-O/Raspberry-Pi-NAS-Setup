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
   5. Start and enable Samba service - **sudo systemctl restart smbd**, **- sudo systemctl enable smbd**
   6. Now we can setup security measures.
  
3. **Security measures**
   1. **Install firewall (Uncomplicated Firewall)** - **sudo apt install ufw**
   2. Allow Samba access within your home network - **sudo ufw allow from "your_home_ip_network" to any port 445**
   3. Enable your **firewall** - **sudo ufw enable**
   4. This setup will enable connection to Raspberry Pi **inside your network**.
   5. Access **from outside the network** is blocked unless additional rules are implemented. 

4. **OpenMediaVault setup**
   1. Open terminal and install your OpenMediaVault with this command
    - **sudo wget -O - https://raw.githubusercontent.com/OpenMediaVault-Plugin-Developers/installScript/master/install | sudo bash**
   3. Once the installation is done, terminalmight  stops. Raspberry Pi will also change its Ip adress.
   4. In router settings, you will find new Ip of your Raspberry Pi and enter this adress to your web browser.
   5. Once OpenMediaVault web will show, you will sign in with user name **admin** and password **openmediavault**
   6. Change your password immediately after logged in.
   7. Go into *Storage - File System*. There you can mount your disk, you will use for storage.
   8. Move to *Shared folders* and **create your shared folder**.
   9. Unders *Services* **enable NFS and SMB** as needed.
   10. Then in top right corner press **Apply** and now you should be able to acces your shared folder.
   11. You can also setup your firewall rules in *Network - Firewall*.

5. **Acces to your folders**
   1. This section is divided into two parts. 
   2. **Windows part**
   3. Open **File Explorer**.
   4. Right click on *This PC* and select **Add network location**.
   5. For address type - **\\"ip_address_of_raspberry"\"shared_folder_name"**.
   6. Enter your **user_name** and **password**.
   7. Your shared folder should now be accessible in *This PC*.
   8. **UNIX-based part**
   9. Open **Finder** on macOS or your **File Manager** on linux.
   10. Click *Go* and then **Connect to server**.
   11. Enter your Ip address - **smb://"ip_address_of_raspberry"/"shared_folder_name"** or **nfs"//.../...***. Depends on         what sharing protocol are you using.
   12. Sign in with your data.
   13. Your folder should now be mounted in your computer.
  
  
