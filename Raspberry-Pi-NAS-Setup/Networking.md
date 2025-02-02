# Networking Basics

**IP addresses and Subnets**
 1. **IP address** is a unique identifier for a device on a network.
   1. There are two types of IP addresses. IPv4 and IPv6.
   2. **IPv4 structure**
   3. Composed of 32 bits divided into *four octets*. Example- 192.168.0.45
   4. Each IP has two parts. **Network** and **Host** part.
   5. IP addresses are divided into public and private. Private addresses are not reachable from the internet. Public are accessible over the internet.
   6. IP addresses are also grouped into Classes. A, B, C, D and E. Each defining the range of networks and hosts each class can support.

 2. **Subnetting** divides network into smaller more manageable sections called **subnets**.
    1. Each IP has a subnet mask, defining which part belongs to the network.
    2. Subnets help us with easier management and network isolation.
    3. Example - 255.255.0.0

 3. **DHCP (Dynamic Host Configuration Protocol)**
    1. DHCP automatically assigns IP addresses dynamically to devices on the network.
    2. It simplifies IP management.
    3. We can also set static IP for servers, printers or Raspberry Pi, so it is easier to reach.
   
 4. **Ping and Traceroute**
    1. **Ping** tests, if the device is reachable on internet.
    2. *ping 192.168.1.1*
   
    3. **Traceroute** shows how packets fly over the internet to reach the destination.
    4. *traceroute 8.8.8.8*
   
    5. These two commands help us to diagnose connectivity issues.
   
 5. **Port forwarding**
    1. Allows us to make devices accessible through specific ports.
    2. Example is remote access to NAS for sharing files.
    3. It helps with security measures.
   
 6. **VLAN (Virtual Local Area Network)**
    1. Helps us isolate devices into separate. virtual networks for improved security and traffic.
    2. We need VLAN capable switches or routers.
    3. It really help us with unauthorized access.
   
 7. **Security**
    1. Always use really strong passwords for everything.
    2. You can also consider using VPNs for even more security.
    3. You can regularly monitor unusual activity or unauthorized access attempts.
