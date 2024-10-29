---
tags:
  - steganography
---

John the Ripper is a fast password cracker, currently available for many flavors of Unix, Windows, DOS, and OpenVMS. Its primary purpose is to detect weak Unix passwords. Besides several crypt(3) password hash types most commonly found on various Unix systems, supported out of the box are Windows LM hashes, plus lots of other hashes and ciphers in the community-enhanced version. John can almost crack all password encrypted archives.

### Installation
	sudo snap install john-the-ripper

### Usage
	zip2john file.zip

### Example
```bash 
$ zip2john flag.zip
flag.zip:$zip2$*0*1*0*47690c81c096c3c8*4d21*1f*7b9718219de608c6c2d860c4cf5566471d3d4bb5c73b5449ab75ac357c185c*6114d207125db9159c6a*$/zip2$:::::flag.zip
```

```bash
$ zip2john flag.zip >> hash.txt
```

```bash
$ john hash.txt

Warning: detected hash type "ZIP", but the string is also recognized as "zip-opencl"
Use the "--format=zip-opencl" option to force loading these as that type instead
Loaded 1 password hash (ZIP, WinZip [PBKDF2-SHA1 8x SSE2])
Will run 8 OpenMP threads
Press 'q' or Ctrl-C to abort, almost any other key for status
123321           (flag.zip)
1g 0:00:00:02 DONE 2/3 (2019-04-26 17:31) 0.4651g/s 16946p/s 16946c/s 16946C/s 123456..MATT
Use the "--show" option to display all of the cracked passwords reliably
Session completed
```

So the password found is 123321, similarly we can crack the archive compressions like 7z, Rar.