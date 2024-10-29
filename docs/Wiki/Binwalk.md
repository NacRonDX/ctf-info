---
tags:
  - steganography
---

It is a tool used mainly for searching embedded files and executable code within another data file.

### Installation
	sudo apt install binwalk

### Usage
	binwalk -e <file-name>

![[binwalk.png]]

Here in the above image, we see that there is a 'jpg image' that has a compressed 'images' in it and we see that it is, it is embedded within the jpg image file. To extract it we can make use of a carving tool **dd**. It can carve out data from specific offsets that are passed as arguments to the tool along the with the file that needs to be read. Give the following command:
	dd if=deeper.jpg of=image1.jpg bs=1 skip=202

Where at _if=_ the file from which data has to be extracted is passed as an argument and _of=_ has the name of the file that we give after extraction. _skip=_ is the offset of the file that has to be read and _bs=_ i the byte skip argument that specifies the frequency of reading data from the given file.