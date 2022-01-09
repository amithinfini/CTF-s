The password for the next level is stored in the file data.txt in one of the few human-readable strings, preceded by several ‘=’ characters.

UsvVyFSfZZWbi6wgC7dAFyFuR6jQQUhR

ls -alh
file *
# data is binary file
strings data.txt | grep -E "=+"