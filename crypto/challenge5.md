# Challenge 5 

ِAfter looking at the python code, i thought it might be vulnerable to weak key attack, so i tried it.

```python
from Crypto.Cipher import DES
import base64
import binascii
keys=["0101010101010101","FEFEFEFEFEFEFEFE" ,"E0E0E0E0F1F1F1F1","1F1F1F1F0E0E0E0E"]
cipher="kIi6qSDhcSVErHbkpy/M1hRHfDpr8TiaGbAIrKUXooxSXwNnaeJgTQ=="

def dec(plaintext,key): 
    cipher1=base64.b64decode(plaintext)
    cipher = DES.new(key, DES.MODE_ECB)
    return cipher.decrypt(cipher1)

for i in keys:
 key = binascii.unhexlify(i)
 print (i," : ",dec(cipher,key)
```
the output is : 
```
0101010101010101  :  b'\xaeS\x0b\xb7k\xc0^\x1e\x0c\xbf\x82\xfa\xed\xc9e\xc5V\xda\n\xfc\x0f\x18\x8a\x9f\x8c\x8f\xf4\x05\xf4\x13\x06\x0e\xe0\x00\xa3\x1d\xe0\x96\x10,'
FEFEFEFEFEFEFEFE  :  b'ASCWG{Welcome_to_des_weak_key_attack}***'
E0E0E0E0F1F1F1F1  :  b"\xc2\xecP\x99\x06\x7f\xf7\xf8\xfa\x0c\xa5/]\x9f\x9fz\xdf'cyc\x1dx\x1a5\x97s\x12@\xee@\x9cwX\xa74\x8e\x07\xe6r"
1F1F1F1F0E0E0E0E  :  b'\x17\x90\xca\xf9\x8d\x1dmD+\x02\xfbr\x

```


**ASCWG{Welcome_to_des_weak_key_attack}**