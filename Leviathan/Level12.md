## Level 1 to 2

Using previosuly saved file *leviathan1*\
To Login:
```bash
sshpass -p $(cat leviathan1) ssh -p 2223 leviathan1@leviathan.labs.overthewire.org
```


List the files and find *check* with setuid.
Executing *check* asks for password which is unknown for now
```bash 
./check
```


Trying to find the right password:
```bash
strings check |more
```
Tracing the execution:
```bash
ltrace ./check
```
Asks for password, enter some password.\
Gives out-
```strcmp("hel", "sex")```\
So the password must be **sex**

Now execute the program *check* and enter the password obtained above, you'll enter into a shell, execute ```$whoami``` to check on the user.

Get the password of user# leviathan2
```bash
$ cat /etc/leviathan_pass/leviathan2
```

Save the password to file *leviathan2*

At last ```exit``` and ```logout```