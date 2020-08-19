# Challenge 4 

[Challenge Link](https://github.com/ascwg/Challenges/blob/master/Crypto/Challenge%204)

We first create an account and see the cookies, when we try to increase the cookie value, we got invalid padding.

![](../images/challenge_4_1.jpg)

So, it's AES CBC mode with wrong implementation, this challenge is Padding Orcale Attack.

Now, Let's use padbuster tool to get the admin cookie.

![](../images/challenge_4_3.png)

![](../images/challenge_4_4.png)

Admin cookie : `GO2kOl%2Bzii%2Fh1kIPhNYjKwAAAAAAAAAA`.

![](../images/challenge_4_5.jpg)

And we got the flag! 

![](../images/challenge_4_6.jpg)

**ASCWG{74af12231bd03f7bb5d79e0396e3b716e6dea3ef8c67e0b50e735c40bd42ffb9}**

