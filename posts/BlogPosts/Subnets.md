Steps:
1. Convert Address and Mask to Decimal
2. Calculate the Network Address: If the Mask is 255, Bring Down the Adress. If the Mask is 0 use 0 (Other Numbers Refer to Chart 2)
3. Calculate the Broadcast Address: If the Mask is 255, Bring Down the Adress. If the Mask is 0 use 255
4. First IP:Network Address +1
5. Last IP:Broadcast Address -1

Chart 1:

|Column 1|Column 2|Column 3|Column 4|Mask|Network|Addresses|
|--------|--------|--------|--------|----|-------|---------|
|/1      |/9       |/17     |/25     |128 |2      |128     |
|/2      |/10      |/18     |/26     |192 |4      |64      |
|/3      |/11      |/19     |/27     |224 |8      |32      |
|/4      |/12      |/20     |/28     |240 |16     |16      |
|/5      |/13      |/21     |/29     |248 |32     |8       |
|/6      |/14      |/22     |/30     |252 |64     |4       |
|/7      |/15      |/23     |/31     |254 |128    |2       |
|/8      |/16      |/24     |/32     |255 |256    |1       |

Chart 2:
![image](https://user-images.githubusercontent.com/66635295/164542668-3a6305d5-e2c9-4990-8bd3-8d19509cd2e8.png)


Examples:



Address: 165.245.10.77/24

|Address|165|245|10|77|
|-------|---|---|--|--|
|Mask   |255|255|255|0|
| | &#8595;| &#8595;| &#8595;| &#8595;|
|Network Adress|165|245|10|0|
|Broadcast Address|165|245|10|255|
|First Ip|165|245|10|1|
|Last Ip|165|245|10|254|


1. Column 3: /24  Mask:255 
2. Bring Down Address and use 0
3. Bring Down Address and convert  0
4. Network Address +1
5. Broadcast Address -1




Address: 165.245.10.77/26

|Address|165|245|10|77|
|-------|---|---|--|--|
|Mask   |255|255|255|192|
| | &#8595;| &#8595;| &#8595;| &#8595;|
|Network Adress|165|245|10|64|
|Broadcast Address|165|245|10|127|
|First Ip|165|245|10|65|
|Last Ip|165|245|10|126|


1. Column 4: /26  Mask:192 
2. Bring Down Address, Mask 192 has Address 64: 77 falls into row 64
3. Bring Down Address Last Number in Row is 127
4. Network Address +1
5. Broadcast Address -1

Cheat Sheet:   
*Subtract 2 from Host  
![image](https://user-images.githubusercontent.com/66635295/164549637-e75180cc-d2e5-4972-8df4-723996b0b42e.png)


