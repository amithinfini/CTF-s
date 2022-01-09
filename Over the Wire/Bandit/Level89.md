The password for the next level is stored in the file data.txt and is the only line of text that occurs only once

ssh -p 2220 bandit8@bandit.labs.overthewire.org
cvX2JJa4CFALtqS87jk27qwqGhBM9plV

ls -alh
cat data.txt | sort | uniq -u