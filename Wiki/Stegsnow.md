---
tags:
  - steganography
---

_Stegsnow_ is a tool for concealing messages in text files by appending tabs and whitespaces at the end of lines.The encoding used by snow relies on the fact that whitespaces and new lines won't be displayed in text editors.

### Installation
	sudo apt install stegsnow

### Usage
#### Encryption
	stegsnow -C -m "Attack At Dawn" -p "hail-hydra" NewColossus.txt NewColossusMod.txt

#### Decryption
	stegsnow -C -p "hail-hydra" NewColossusMod.txt Encoded Message: Attack At Dawn`
