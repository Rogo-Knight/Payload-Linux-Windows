# Payload-Linux-Windows
Acquiring Root Privilege or NT-Authority System
## 🖥️ Install xfreerdp3 on Kali Linux

### 1. Update Package Lists
Ensure your local repository lists are current before installing new packages.
```bash
sudo apt update
sudo apt install -y freerdp3-x11
xfreerdp3 /version
xfreerdp3 /v:<Target_IP> /u:<Username> /p:<Password> /cert:ignore /tls:seclevel:0 +clipboard /dynamic-resolution
```

## 🔑 SSH Connection with Legacy Algorithms

### 1. Bypass Key and Cipher Mismatches
Use these flags when connecting to older legacy targets.
```bash
ssh -o HostKeyAlgorithms=+ssh-rsa -o PubkeyAcceptedAlgorithms=+ssh-rsa <Username>@<Target_IP>
```
## 🔍 System Enumeration

### 1. OS & Hardware Information
```bash
hostname
uname -a
lscpu
cat /proc/version
```
### 2. Process Monitoring
```bash
ps aux
ps aux | grep root
```
## 👥 User Enumeration

### 1. Current Privileges & Group Membership
```bash
whoami
id
sudo -l
```
### 2. Local Users, Groups & History
```bash
cat /etc/passwd
cat /etc/group
cat /etc/shadow
last
```
### 3. File Permissions
```bash
ls -l
```
## 🌐 Network Enumeration

### 1. Interface & IP Configurations
```
ip addr
hostname -I
```

### 2. Active Connections & Listening Ports
```
ss -tulnp
netstat -antp
```

### 3. Routing & Neighbor Tables
```
ip route
ip neigh
```
