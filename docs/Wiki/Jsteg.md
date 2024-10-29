---
tags:
  - steganography
---

Jsteg is a package for hiding data inside JPEG files with a technique known as [steganography](https://en.wikipedia.org/wiki/Steganography). This is accomplished by copying each bit of the data into the least-significant bits ([LSB](https://en.wikipedia.org/wiki/Bit_numbering)) of the image. The amount of data that can be hidden depends on the file size of the jpeg; it takes about 10-14 bytes of jpeg to store each byte of the hidden data.

### Installation
```bash
$ sudo wget -O /usr/bin/jsteg https://github.com/lukechampine/jsteg/releases/download/v0.3.0/jsteg-linux-amd64
$ sudo chmod +x /usr/bin/jsteg
$ sudo wget -O /usr/bin/slink https://github.com/lukechampine/jsteg/releases/download/v0.3.0/slink-linux-amd64
$ chmod +x /usr/bin/slink
```

### Usage
	 jsteg

![[jsteg_info.png]]

### Revealing data
	jsteg reveal <in.jpg> <output file name>