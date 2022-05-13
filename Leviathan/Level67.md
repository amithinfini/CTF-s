## Level 5 to 6


To Login:
```bash
sshpass -p $(cat leviathan6) ssh -p 2223 leviathan6@leviathan.labs.overthewire.org
```

List out the files and you will find a setuid ELF *leviathan6* which has to be executed along with a 4 digit code.

```bash
for i in {0000..9999}; do echo $i; ./leviathan6 $i; done
```

you will enter into shell of leviathan7\
can be veirified with
```bash
whoami
```
```bash
cat /etc/leviathan_pass/leviathan7
```

At last ```exit``` and ```logout```