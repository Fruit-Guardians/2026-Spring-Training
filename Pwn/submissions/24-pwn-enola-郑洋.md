# 1，环境安装

![image-20260418182020521](https://gangtiexia.oss-cn-shenzhen.aliyuncs.com/image-20260418182020521.png)

在vm里安装的Ubuntu系统，配置的pwn环境，包括工具checksec，gdb，objdump，readelf，ropgadget，python3，pwntools，strace，ltrace

### 1.基本指令

#### 1.Linux常用指令

ls，列出目录内容

cd，切换当前工作目录

cat，查看文件内容

find，查找文件

grep，在文件中搜索特定字符串

file，查看文件类型

objdump，反汇编二进制文件

readelf，显示ELF文件信息

chmod，修改文件权限

cp/mv/rm，复制/移动/删除文件

touch，创建空文件

mkdir，创建目录

#### 2.网络连接

nc，连接远程靶机或开启端口监听

ping，检查网络连通性

ifconfig/ip，查看和配置网络接口信息

wget/curl，下载文件

#### 3.进程与系统信息

ps，显示当前进程状态

top/htop，动态显示进程状态和系统资源使用情况

kill，终止进程

uname，打印系统信息

env，查看环境变量

set，显示shell变量和环境变量

export，设置环境变量

#### 4.权限管理

sudo，用root权限执行命令

su，切换用户身份

chown，改变文件所有者

chgrp，改变文件所属组

### 2基本步骤

检查保护机制checksec pwn_me

查看文件类型：file pwn_me

尝试运行（如果需要先给权限）：chmod +x pwn_me-> ./pwn_me

反汇编寻找可疑函数：objdump -d pwn_me | grep -A 10 -B 2 "gets"(查找危险函数)【此步骤一般使用IDA软件完成，更加方便】

用 gdb 调试：gdb ./pwn_me-> (gdb) r(运行)

编写好 exp.py 后利用：python3 exp.py

成功后获取flag：如果 exploit 成功获得了 shell，常用 cat命令读取 flag。

#### 1checksec命令

checksec --file=/path/to/binary

- **`RELRO`(Relocation Read-Only)**:
  - `Partial RELRO`: GOT (Global Offset Table) 部分可写，较容易利用 GOT 覆写攻击。
  - `Full RELRO`: GOT 完全只读，有效防止 GOT 覆写攻击，但会略微增加启动开销。
- **`STACK CANARY`**:
  - `Canary found`: 启用了栈溢出保护（栈金丝雀）。在函数返回前验证栈上的特定值是否被改变，用于检测栈溢出攻击。
  - `No canary found`: 无栈保护，存在栈溢出漏洞时更容易利用。
- **`NX`(Non-eXecutable)**:
  - `NX enabled`: 数据区域（如栈、堆）不可执行。防止将 shellcode 写入数据区后跳转执行。
  - `NX disabled`: 数据区域可执行，为攻击者提供了便利。
- **`PIE`(Position-Independent Executable)**:
  - `PIE enabled`: 程序代码段、数据段的加载地址随机化。要求攻击者利用信息泄露等手段获取地址，增加了利用难度。
  - `No PIE`: 程序加载基址固定，便于攻击者计算 gadgets 和函数的准确地址。
- **`Symbols`**:
  - 表示是否包含调试符号（如函数名、变量名）。`Stripped`（已剥离）会增加分析难度，`Not Stripped`（未剥离）则更易于分析。

#### 2.gdb

用法：gcc -g -o program program.c

- **启动与运行**
  - `gdb ./program`: 启动调试。
  - `(gdb) run <arg1> <arg2>`: 运行程序，可带参数。
  - `(gdb) start`: 在主函数入口暂停，类似在 `main`函数开头下了断点。
- **断点控制**
  - `(gdb) break main`: 在 `main`函数开头设置断点。
  - `(gdb) break *0x400512`: 在指定地址设置断点。
  - `(gdb) info breakpoints`: 查看所有断点信息。
  - `(gdb) delete 1`: 删除编号为 1 的断点。
- **执行控制**
  - `(gdb) continue`: 继续运行直到下一个断点或程序结束。
  - `(gdb) nexti`(`ni`): 执行一条**汇编**指令，**不**进入函数调用。
  - `(gdb) stepi`(`si`): 执行一条**汇编**指令，**会**进入函数调用内部。
  - `(gdb) finish`: 继续运行直到当前函数返回。
- **查看信息**
  - `(gdb) info registers`: 查看所有寄存器的当前值。
  - `(gdb) x/20wx $esp`: 检查内存。`20wx`表示以 4 字节十六进制格式显示 20 个字。
    - 格式语法: `x/[数量][格式][单位] <地址或表达式>`
    - 常用格式: `x`(十六进制), `i`(指令), `s`(字符串)
    - 常用单位: `b`(字节), `h`(半字，2字节), `w`(字，4字节), `g`(巨字，8字节)
  - `(gdb) disassemble main`: 反汇编 `main`函数。
  - `(gdb) print $eax`: 打印 `eax`寄存器的值。
  - `(gdb) backtrace`(`bt`): 显示当前的调用栈（函数调用链），在分析崩溃时非常有用。



#### 3ropgadget

ROPgadget --binary ./vuln_program

常用

- `--binary <文件>`: 指定要分析的二进制文件。
- `--opcode <字节序列>`: 搜索包含特定操作码（机器码）的 gadget（例如 `--opcode c3`搜索 `ret`）。
- `--only "pop|ret"`: 只显示包含特定指令的 gadgets。
- `--string <字符串>`: 在可执行段中搜索指定的字符串（例如 `--string "/bin/sh"`）。
- `--nojop`: 不显示 JOP gadgets (以 `jmp`等指令结尾的 gadget)。

输出会列出所有找到的 gadgets 及其地址

#### 4，file

file ./pwn_me

# 2.栈溢出

栈，先进后出

C语言中使用PUSH来将数据压入栈中，使用POP来将数据弹出。

栈一般用于存放局部变量，如函数的参数、返回地址、局部变量等，由系统自动分配和释放

递归调用时也是使用栈作为一个缓冲区

栈溢出是缓冲区溢出中的一种。函数的局部变量通常保存在栈上。如果这些缓冲区发生溢出，就是栈溢出。最经典的栈溢出利用方式是覆盖函数的返回地址，以达到劫持程序控制流的目的。

栈溢出指的是程序向栈中某个变量中写入的字节数超过了这个变量本身所申请的字节数，因而导致与其相邻的栈中的变量的值被改变（覆盖）。是一种特定的缓冲区溢出漏洞，类似的还有heap、bss溢出等。

##### 运用前提

程序必须向栈上写入数据

程序对某个函数或者某个模块的输入数据的大小没有控制得当

##### 危险函数

输入：

`gets()`：直接读取一行，到换行符’\n’为止，同时’\n’被转换为’\x00’；scanf()，格式化字符串中的%s不会检查长度；
`vscanf()`：同上。
输出：
`sprintf()`：将格式化后的内容写入缓冲区中，但是不检查缓冲区长度
字符串：
`strcpy()`：遇到’\x00’停止，不会检查长度，经常容易出现单字节写0（off by one）溢出；
`strcat()`：同上。

##### 覆盖位置

覆盖函数返回地址

覆盖栈上所保存的BP寄存器的值

根据现实执行情况，覆盖特定的变量或地址的内容，可能导致一些逻辑漏洞的出现

##### 利用思路

寻找危险函数

找到所操作地址距离我们需要覆盖地址的距离

# 3.题目

##### 1.![image-20260418195503387](https://gangtiexia.oss-cn-shenzhen.aliyuncs.com/image-20260418195503387.png)

在Ubuntu中用nc连接后，ls出文件内容，cat flag便得到了flag

##### 2.3题目找不到， https://newstar.games关闭了

##### 
