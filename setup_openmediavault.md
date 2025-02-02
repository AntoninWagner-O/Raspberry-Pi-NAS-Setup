**OpenMediaVault setup**
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
