---
tags:
  - steganography
---

A tool to test PNG image files for corruption, display size, type, compression info.

pngcheck is the official PNG tester and debugger. Originally designed simply to test the CRCs within a PNG image file (e.g., to check for ASCII rather than binary transfer), it has been extended to check and optionally print almost all the information about a PNG image and to verify that it conforms to the [PNG specification](http://www.libpng.org/pub/png/spec/1.2/PNG-Structure.html). It also includes partial support for MNG animations.

It can dump the chunk-level information in the image in human-readable form. For example, it can be used to print the basic stats about an image (dimensions, bit depth, etc.); to list the color and transparency info in its palette; or to extract the embedded text annotations. All PNG and JNG chunks are supported, plus almost all MNG chunks (everything but PAST, DISC, tERm, DROP, DBYK, and ORDR). This is a command-line program with batch capabilities.

### Installation
	sudo apt install pngcheck

### Common commands
	pngcheck -v image.png

### Things to look out for
* The size of the second to last **IDAT** chunk not being max value -> [[Hidded data in PNG IDAT chunk]]