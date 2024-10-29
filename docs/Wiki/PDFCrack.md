---
tags:
  - steganography
---

PDF Crack is a tool for recovering the pass for **Encrypted PDF files**. **Encrypted files** means the metadata of the file was encrypted with some characters.

It has some special features like:

- Checks with the system password and also the user provided password.
- It can crack password by **brute-forcing** method only for character sets and only when we provide the maximum and minimum length of the password.
- Searches the password from the **wordlist**.
- Optimized search for owner-password when user-password is known.

### Installation
	sudo apt-get install pdfcrack

### Usage
The general usage of pdfcrack for brute-forcing
	`pdfcrack -f <file_name>`

The general usage of pdfcrack when we provided a wordlist
	`pdfcrack -f <file_name> -w <location_of_wordlist_file>`

If you unfortunately, click **ctrl+c** then it will save the process until you clicked into an another file called **savedstate.sav** in the directory where the PDF is present or the current directory.