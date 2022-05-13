## Level 3 to 4


To Login:
```bash
sshpass -p $(cat leviathan3) ssh -p 2223 leviathan3@leviathan.labs.overthewire.org
```
List the files on leviathan3 home and you will see a setuid ELF file *level3*.\
On executing asks for password, to find the right password ltrace and you will see the entered strings are compared again **snlprintf**. So, **snlprintf** should be the right password.

```bash
ltrace ./level3
```
> Enter some password and see it get compared with **snlprintf**

Execute ```./level3``` and on entering the right password you are put into leviathan4 shell, cat the password file at ```/etc/leviathan_pass/leviathan4``` to get the password for next level- leviathan4

```bash
cat /etc/leviathan_pass/leviathan4
```

Save the password to file *leviathan4*

At last ```exit``` and ```logout```