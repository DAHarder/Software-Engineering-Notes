# Basic Commands

## IP Setup Commands
```bash
#Used to list and modify interfaces on the host
ip link

#see ip addresses assigned to the interfaces
ip addr

#set ip addresses on interfaces
ip addr add 192.168.1.10/24 dev eth0

#View routing table
ip route

#add entries into routing table
ip route add 192.168.1.0/24 via 192.168.2.1

#check if ip forwarding is configured (if host is configured as a router)
cat /proc/sys/net/ipv4/ip_forward
```

## Network Information Commands
### **nslookup**
```bash
#query hostname from a DNS server
nslookup www.google.com
```
![[Pasted image 20230126161607.png]]

### **dig**
```bash
#Similar to nslookup but returns more information
dig www.google.com
```
![[Pasted image 20230126161622.png]]

# DNS

**/etc/hosts**
>This file is similar to the hosts file in windows
![[Pasted image 20230126161633.png]]

/etc.resolve.conf
>DNS resolution configuration file - configure for hosts to connect to DNS server
![[Pasted image 20230126161640.png]]

/etc/nsswitch.conf
>This file configures whether to check the hosts file first, or the DNS server first for hostname mapping to ip address (the default is to check the hosts file first and use whatever is in there)
![[Pasted image 20230126161647.png]]