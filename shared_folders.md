**Acces to your folders**
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
