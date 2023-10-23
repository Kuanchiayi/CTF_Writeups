# Flag_shop

## Description
```There's a flag shop selling stuff, can you buy a flag? ```

## Solve
```total_cost```被聲明為一個```int```，其範圍介於```-2,147,483,648```到之間```2,147,483,647```。整數使用第一位來儲存是負數還是正數，```0```表示正數，```1```表示負數。如果將結果加總並儲存在有符號整數中1會發生什麼？2,147,483,647那麼第一位從```0```到```1```，這意味著該數字現在是負數。

利用整數溢位原理，。我們可以用它來溢出```total_cost```變數並增加我們的帳戶餘額。但又不能太大以至於它也會溢出我們的```account_balance```. 我們使用```3000000```。

![image](https://github.com/Kuanchiayi/CTF_Writeups/blob/main/General%20Skill/flag_shop/%E8%9E%A2%E5%B9%95%E6%93%B7%E5%8F%96%E7%95%AB%E9%9D%A2%202023-10-23%20133703.png?raw=true)
