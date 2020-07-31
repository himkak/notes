# Bit Manipulation

## 6 bit operators are there :

### AND
 & : And : Its a binary operator
 - 0 & 0 : 0
 - 0 & 1 : 0
 - 1 & 0 : 0
 - 1 & 1 : 1

### OR
 | : Or : Binary Operator
 - 0 | 0 : 0
 - 0 | 1 : 1
 - 1 | 0 : 1
 - 1 | 1 : 1

### NOT
 ~ : Negation : Unary operator
 ~0 : 1
 ~1 : 0

### XOR
 ^ : Xor : Either of them should be 1, not both then 1
 - 0 ^ 0 : 0
 - 0 ^ 1 : 1
 - 1 ^ 0 : 1
 - 1 ^ 1 : 0

### Left Shift
 << : Left shift
 Eg : 5 = 101 base 2
 101<< : 010 
 - Move all elements left and fill the right most bit with 0. The left most element will be removed.
 - It is bit complex as it depends on the no of bits u r using to represent a number
 - 5 in bit s to base 2 = 00000101
 - 00000101<< = 00001010 = 10
 - Left shift is a multiplication by 2
	 ```
	1 << 1 = 2 = 21
	1 << 2 = 4 = 22 1 << 3 = 8 = 23
	1 << 4 = 16 = 24
	…
	1 << n = 2n
	 ```

### Right Shift
 >> : RIght shift
 - Right shifting operator divide a number by 2
 - Right shift is equivalent to dividing the bit pattern with 2k ( if we are shifting k bits ).
	 ```
	4 >> 1 = 2
	6 >> 1 = 3
	5 >> 1 = 2
	16 >> 4 = 1
	 ```
 
## Check if a number is odd or even
- we can do it using % but its very slow
- Better option is to use bit manipulation
- when u do a binary number & 1, it either gives 0 or 1
- 13 & 1 = 01101 & 1 = 00001 = odd & 1 = 1
- 20 & 1 = 10100 & 1 = 00000 = even & 1= 0

**odd & 1 =1, even & 1=0**
```
if(n&1==1){
//odd number
}else {
// even number
}
```
- It works for both even and odd


## Convert a to b using or operator
- a|X=b
- We need to count the no of X that exists to convert a to b using or(|)
- Eg : convert 2 to 3
```	
	2|1=3
	2|2=2
	2|3=3
```


- Brute force : run a for loop from 1 to b and do : if(a|i==b)

- Efficient solution: 
- 2 = 010
- 3 = 011
- Now we check who many ways to covert every bit to other and then multiple all those numbers.
	```
	010      we check from right to left, so 1st we have to convert 0 to 1. 0->1 = 1 way, that is 0|1=1. 	Next 1->1 = 2 ways : 1|1=1, 1|0=1, so ways. Next 0->0= 1 way
	011
   -----
   1*2*1 = 2 ways
	```
- So answer is 2 ways
- Ref : https://www.youtube.com/watch?v=RYG_3zyi608&list=PLfQN-EvRGF39Vz4UO18BtA1ocnUhGkvk5&index=3

- Eg 2:
![Convert A to B using or](https://github.com/himkak/my-notes/blob/master/AlgoDS/bit-manipulation/ConvertAtoBusingOr.JPG)

## Check if a number is pow of 2
- x & (x-1) == 0


##  Count the number of ones in the binary representation of the given number.
```
int count_one (int n)
        {
            while( n )
            {
            n = n&(n-1);
               count++;
            }
            return count;
    }
```


# Tricks 
**odd & 1 =1, even & 1=0**

**Left shift is equivalent to multiplying the bit pattern with 2 pow k**


# References
- https://www.hackerearth.com/practice/basic-programming/bit-manipulation/basics-of-bit-manipulation/tutorial/
