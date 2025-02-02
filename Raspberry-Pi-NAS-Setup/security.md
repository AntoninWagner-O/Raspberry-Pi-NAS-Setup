**Security measures**
   1. **Install firewall (Uncomplicated Firewall)** - **sudo apt install ufw**
   2. Allow Samba access within your home network - **sudo ufw allow from "your_home_ip_network" to any port 445**
   3. Enable your **firewall** - **sudo ufw enable**
   4. This setup will enable connection to Raspberry Pi **inside your network**.
   5. Access **from outside the network** is blocked unless additional rules are implemented. 
