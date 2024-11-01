### Description
Don't try to throw random tools at this poor image. Go back to the basics and learn the detection techniques.

Good luck!<br>

Format : **Hero{}**<br> 
Author : **Thibz**

### Files

[[lsd3_secret.png|secret.png]]

### Write up

This challenge is similar to last year's, but a little tougher.

In order to solve this challenge, it is enough to look at the title to give us an interesting lead: the LSD (Least-Significant Bit).
The description tells us that it is useless to launch automatic scripts and that we have to think about it, too bad.

There is a fairly simple way to detect traces of LSB in an image. 

Some basics before going further. A colour image is made up of pixels. Each pixel is composed of three RGB layers for Red Green Blue. 
In computing, each of the three layers is a value between 0 and 255. 

![[lsd3_pixels.jpg]]

Thus, to have a red pixel, the pixel must have the value (255,0,0) which could be translated as 100% red, 0% green and 0% blue. Yellow is a mixture of red and green. A yellow pixel will therefore have a value of (255,255,0) which is translated as : 100% red, 100% green and 0% blue.

We also know that in computing, everything is binary. So a red pixel is coded like this: 

```
R : (11111111)
G : (00000000)
B : (00000000)
```

What happens if we set the Least Significant Bit to 0 on the Red layer? 

Color with red value at 255 :
![[lsd3_FullRed.png]]

Color with red value at 254 :
![[lsd3_LSBRed.png]]

The two colours are different but to the naked eye the two colours look identical. This is the principle on which the technique is based, we will hide our message in the least significant bits of an image. 

Now that we know how it works, let's look at how we can detect it. The aim is to make this normally invisible change much more visible to the naked eye. Filters exist to do exactly what we want. These filters will display the image according to the value of each of the 8 bits of each layer. 

I use [AperiSolve](https://www.aperisolve.com/) which allows me to display the image according to the 16 filters displayed.

The first filter on the blue layer : 

![[lsd3_diag_lsb.png]]

Each of these images will keep one of the 8 bits of the blue layer while setting all others to 0. 

The top left image will keep only the least significant bit and set everything else to 0. We realise that a strange diagonale appears, just as if the least significant bits were not all the same on the blue layer... 

We just need to iterate over this diagonale and recover all the least significant bits of the blue layer.

```python
def stringToFile(string, dst):
    file = open(dst, 'w')
    file.write(string)
    file.close()

def binaryToString(binary):
    return ''.join([chr(int(binary[i:i+8], 2)) for i in range(0, len(binary), 8)])

def decode(src):
    print("[-] Decoding... ")
    
    extracted_bin = ""
    img = Image.open(src, 'r')

    width, height = img.size
    print("[-] Image size: {}x{}".format(width, height))
    for x in range(0, 1500): # The diagonale has 1500 pixels
        pixel = list(img.getpixel((x, x)))
        # Pixel[2] is the blue plane
        extracted_bin = extracted_bin + str((pixel[2] & 1))
    
    stringToFile(binaryToString(extracted_bin), "extracted.txt")
    print("[-] Message extracted !")
    print("[-] Message saved as extracted.txt")

```

### Flag

```"Hero{L5B_D14G0N4L3}"```