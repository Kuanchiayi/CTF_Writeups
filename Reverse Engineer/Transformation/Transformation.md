# Transformation

## Description
```I wonder what this really is... enc ''.join([chr((ord(flag[i]) << 8) + ord(flag[i + 1])) for i in range(0, len(flag), 2)])```

## Solution
這段程式碼使用chr()和ord()，顯示從decimal轉成ascii。
```
''.join([chr((ord(flag[i]) << 8) + ord(flag[i + 1])) for i in range(0, len(flag), 2)])
```
使用網站[Site](https://www.rapidtables.com/convert/number/ascii-hex-bin-dec-converter.html)將enc解碼得到
> 28777 25455 17236 18043 12598 24418 26996 29535 26990 29556 13108 25695 28518 24376 24421 14128 13154 13368 13949

使用'pi'來驗證這段程式碼
```
>>(ord('p') << 8) + ord('i')
>>28777
```

使用'co'來驗證這段程式碼
```
>>(ord('c') << 8) + ord('o')
>>25455
```

寫了這段程式碼來復原flag
```
str = '灩捯䍔䙻ㄶ形楴獟楮獴㌴摟潦弸彥㜰㍢㐸㙽'
bin = [28777, 25455, 17236, 18043, 12598, 24418, 26996, 29535, 26990, 29556, 13108, 25695, 28518, 24376, 24421, 14128, 13154, 13368, 13949]
result = ''

for i in range(len(str)):
    a = chr(ord(str[i]) >> 8)
    result += chr(ord(str[i]) >> 8) 
    result += chr(bin[i] - (ord(chr(ord(str[i]) >> 8)) << 8))
print(result)
```

# 補充
```
12 << 2
48
```
當我們執行上述語句時，12的實際二進位值為「00 1100」。左移（左移 2 位元）傳回值 48，其二進位值為「11 0000」。
```
48 >> 2
12
```
48的二進位值為“11 0000”，執行上述語句右移（右移2位元）後返回值12，其二進位值為“00 1100”。
