---
tags:
  - steganography
---

It is a tool used to crack passwords in files which contains hidden data.

### Installation
For installing stegcracker we would require steghide, for installing steghide try
```bash
$ sudo apt-get install steghide -y

$ pip3 install stegcracker
```

### Usage
	stegcracker <file> [<wordlist>]

For the wordlist, an example is to use [rockyou.txt](https://www.google.com/url?sa=t&source=web&rct=j&opi=89978449&url=https://github.com/brannondorsey/naive-hashcat/releases/download/data/rockyou.txt&ved=2ahUKEwjg95rgxrGJAxVR0AIHHapvOYEQFnoECAoQAQ&usg=AOvVaw3snAERl1mU6Ccr4WFEazBd)