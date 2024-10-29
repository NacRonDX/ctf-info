---
tags:
  - steganography
---

Zsteg is also a tool like Jsteg but it is used to detect _LSB_ steganography only in the case of **PNG** and **BMP** images.

### Installation
```bash
sudo apt install ruby
sudo gem install zsteg
```

### Usage
	zsteg <filename>

When a good ordering is found 
	`zsteg -a secret200.png -E b1,g,lsb,yx`
#### Used in
* [HeroCTF v5 2023 - LSD#2](https://gitlab.com/cupteam/heroctf2023/-/tree/main/LSD_2?ref_type=heads)