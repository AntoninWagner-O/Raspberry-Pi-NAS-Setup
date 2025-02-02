**Samba setup**
   1. In bash install your Samba - **sudo apt install samba nfs-kernel-server**
   2. Create your *share directory* - **sudo mkdir ~/nas_share**
   3. Edit Samba *configuration file* - **sudo nano /etc/samba/smb.conf**
      
          [nas_share]
            path = /home/"your_user"/shared
            read only = no
            browsable = yes
            valid users = @users
      
   5. Add a Samba user - **sudo smbpasswd -a "your_user"**
   6. Start and enable Samba service - **sudo systemctl restart smbd**, **- sudo systemctl enable smbd**
   7. Now we can setup security measures.
