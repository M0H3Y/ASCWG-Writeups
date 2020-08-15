# Challenge 1

Looking at the code we find that the flag is converted to an integer value and shifted 99998 bits to the left to give the last 200 decimal digits of the value. 

Let's convert the problem into equation:
```
c = flag⋅2^99998mod10^200
```
we try to inverse 2^99998 on F10^200, but they are not coprime so its not possible.

the prime factors of 10 is 2, 5 but φ(2)=1 it will not affect so we choose 5

the equation will be:
```
c=flag⋅2^99998mod5^200
```

using Euler’s theorem, we find :

```
(2^99998)^(−1)mod5^200=(2^99998)^(φ(5^200)−1)=(2^99998)^(5^200−5^199−1)
```
so this is the equation to get the flag:
```
flag=c⋅(2^99998)^(−1)mod5^200
```

```python
c = 46186384884704143502810449626149776675765629346197308004864280982758330594138478052711607866947764263543620513433238646216483214982856318892731845815726243647558073159634372394623630437969797570363392
mod = 5 ** 200
phi = 5 * 200 - 5 * 199 
inv = pow(pow(2, 99998, mod), phi - 1, mod) 
print(((c * inv) % mod).to_bytes(50, byteorder='big'))
```
**ASCWG{Number_Ther0m_1s_1mportanmt_1n_Crypt0_12387}**



