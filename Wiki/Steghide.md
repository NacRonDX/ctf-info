---
tags:
  - steganography
---

Steghide is steganography program which hides bits of a data file in some of the least significant bits of another file in such a way that the existence of the data file is not visible and cannot be proven.

Steghide is designed to be portable and configurable and features hiding data in bmp, jpeg, wav and au files, blowfish encryption, MD5 hashing of passphrases to blowfish keys, and pseudo-random distribution of hidden bits in the container data.

Steghide is useful in digital forensics investigations.

	sudo apt install steghide
	sudo apt install steghide-doc

#### Usage
To embed a secret message into an image
```bash
$ steghide embed -cf image.jpg -ef secret_message.txt
Enter passphrase : ********
Re-Enter passphrase : ********
embedding "secret_message.txt" in "image.jpg"... done
```
To extract the secret message from the image
```bash
$ steghide extract -sf image.jpg
Enter passphrase : ********
wrote extracted data to "secret_message.txt".
```

It is important to note that the password may not always be a plain text sentence. Sometimes it may be hashed. Some examples of hashes include MD5, sha1 etc. We all know that there is no specific way to reverse the hashes. But, there are websites which store hashes of certain commonly used strings.

Some of such websites are:  
1. [HashKiller](https://hashkiller.co.uk/md5-decrypter.aspx)
2. [MD5Decrypt](http://md5decrypt.net/)