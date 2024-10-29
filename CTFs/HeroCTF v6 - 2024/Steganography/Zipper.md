### Description
Some data has been hidden somewhere in this archive, good luck finding it!  
  
Format : **Hero{}**  
Author : **Thibz**
### Files
[secretzip.zip](obsidian://open?vault=CTF&file=CTFs%2FHeroCTF%20v6%20-%202024%2Ffiles%2Fsecretzip.zip)
### Write up
This challenge resides in the fact that we can hide images after a file section right before the 1st central directory header. Then simply update a pointer in an end of central directory record to compensate the shift of the central directory header. When you unzip the archive, the hidden file will be ignored.

We can still see him appear while doing a binwalk.

```bash
$ binwalk -e secretzip.zip 

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             Zip archive data, at least v1.0 to extract, name: whatiszip/
68            0x44            Zip archive data, at least v2.0 to extract, compressed size: 31563, uncompressed size: 33944, name: whatiszip/zipheader.png
31712         0x7BE0          Zip archive data, at least v2.0 to extract, compressed size: 27706, uncompressed size: 28510, name: whatiszip/ZIP.pdf
59493         0xE865          Zip archive data, at least v2.0 to extract, compressed size: 29125, uncompressed size: 31304, name: whatiszip/zipformat.png
88699         0x15A7B         PNG image, 1280 x 720, 8-bit/color RGBA, non-interlaced
90037         0x15FB5         Zlib compressed data, default compression
901578        0xDC1CA         End of Zip archive, footer length: 22
```

We can then extract it with
	`zipography-extract ../secretzip.zip > extracted.png`
### Flag
	Hero{Dont_be_fooled_by_appearances}

### Tools used
* [[Binwalk]]
* [[Zipography]]