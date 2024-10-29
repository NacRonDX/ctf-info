---
tags:
  - steganography
---

Fcrackzip is a password cracking tool for ZIP files. Fcrackzip cracks the password by **Brute-Force Attack** or by a **Dictionary Attack**.

In a **Brute-force Attack** the attacker checks all the known combinations of passwords until the correct password founds.

**Dictionary Attack** involves providing a wordlist which contains a set of commonly used passwords.

### Installation
	sudo apt install fcrackzip

### Usage
The general usage of fcrackzip for brute forcing the password is as follows.
	`fcrackzip -v -b -u <file_name.zip>`

- -v for knowing what's going on in background. Commonly Know as **verbose**.
- -b for **brute-forcing**.
- -u for **unzip**.
- -p for setting the **initial password** for brute forcing or the file to supply password for dictionary attack.
- -D sets **dictionary mode** and reads passwords from a wordlist alphabetically.

The general usage for the dictionary attack is as follows. 
	`fcrackzip -v -u -D -p <path_to_wordlist_file> <file_name.zip>`

The common wordlist which is publicly available is [rockyou](https://github.com/brannondorsey/naive-hashcat/releases/download/data/rockyou.txt).