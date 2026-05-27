### Enumeration
```
nmap -Pn -sC -sV IP
gobuster dir -u http://<MACHINE_IP> -w /usr/share/wordlists/dirb/common.txt
dirbuster
```
### Login
```
xfreerdp3 /u:wade /p:parzival /v:<MACHINE_IP> /cert:ignore /dynamic-resolution +clipboard
```
### Exploitation
```
Find hhupd.exe and run as administrator
Click Show more details, and then click Show information about the publisher's certificate.
In the certificate window, click on the Issued by link.
Inside Internet Explorer, press Ctrl + S (or click File -> Save As)
Filename- C:\Windows\System32\*.*
cmd.exe and run.
