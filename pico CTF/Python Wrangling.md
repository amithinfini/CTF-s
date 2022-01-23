# Python Wrangling

## Description
Python scripts are invoked kind of like programs in the Terminal... Can you run this Python script using this password to get the flag?

script: https://mercury.picoctf.net/static/b351a89e0bc6745b00716849105f87c6/ende.py
pwd: https://mercury.picoctf.net/static/b351a89e0bc6745b00716849105f87c6/pw.txt
flag: https://mercury.picoctf.net/static/b351a89e0bc6745b00716849105f87c6/flag.txt.en


$ wget https://mercury.picoctf.net/static/b351a89e0bc6745b00716849105f87c6/ende.py
$ wget https://mercury.picoctf.net/static/b351a89e0bc6745b00716849105f87c6/pw.txt
$ wget https://mercury.picoctf.net/static/b351a89e0bc6745b00716849105f87c6/flag.txt.en

cat pwd.txt
python ende.py -d flag.txt.en
<paste the pwd>