## Level 4 to 5


To Login:
```bash
sshpass -p $(cat leviathan4) ssh -p 2223 leviathan4@leviathan.labs.overthewire.org
```

List the files in leviathan4 home you will find hidden folder ```.trash``` and setuid ELF ```bin``` in it. Executing ```./bin``` you will get a series of binary digits.
Working on coverting bin to hex and then to ASCII
```bash
./bin
```
```bash
./bin | tr " " "\n"
```
```bash
./bin | tr " " "\n" | while read line; do echo $line;done
```
base convertion using ```bc```
```bash
./bin | tr " " "\n" | while read line; do echo "obase=16;ibase=2;$line" | bc;done
```
```bash
./bin | tr " " "\n" | while read line; do echo "obase=16;ibase=2;$line" | bc;done | tr -d "\n"
```
Convert Hex to ASCII using HexDump
```bash
./bin | tr " " "\n" | while read line; do echo "obase=16;ibase=2;$line" | bc;done | tr -d "\n" | xxd -r -p
```

Save the password to file *leviathan5*

At last ```exit``` and ```logout```