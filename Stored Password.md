### Using `history` command
  ```bash
  $ history  # It will give a large list, simplify it
  $ history | grep password
  mysql -h somehost.local -uroot -ppassword123
  ```
### Using ls -la to open .bash_history
```
$ ls -la
$ cat .bash_history | grep password
mysql -h somehost.local -uroot -ppassword123
```
### Using myvpn.ovpn to open /etc/openvpn/auth.txt
```
$ ls
$ cat myvpn.ovpn
$ cat /etc/openvpn/auth.txt
```
### Using the payload
```
$ find . -type f -exec grep -i -I "PASSWORD" {} /dev/null \;
```
