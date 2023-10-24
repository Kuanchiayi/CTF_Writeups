# Matryoshka doll

## Description
```Matryoshka dolls are a set of wooden dolls of decreasing size placed one inside another. What's the final one? Image: this```

## Solution

Using [Binwalk](https://github.com/ReFirmLabs/binwalk/wiki/Quick-Start-Guide)

```
binwalk dolls.jpg
```
得到，可以發現存在base_image/2_c.jpg，1u/並且未解壓縮
```
DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 594 x 1104, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
272492        0x4286C         Zip archive data, at least v2.0 to extract, compressed size: 378954, uncompressed size: 383938, name: base_images/2_c.jpg
651612        0x9F15C         End of Zip archive, footer length: 22
```
於是將 dolls.jpg 解壓縮
```
unzip dolls.jpg
```
可以發現還有一張 ```2_C.jpg``` 存在base_image底下
```
cd base_image
```
再繼續解壓縮，重複幾次後就能得到 ```flag.txt```
```
cat flag.txt
```

```picoCTF{bf6acf878dcbd752f4721e41b1b1b66b}```

