## 工具安装
### **<font style="color:rgb(31, 35, 40);">浏览器开发者工具 F12</font>**<font style="color:rgb(31, 35, 40);"> </font>**<font style="color:rgb(31, 35, 40);">/查看网页源代码</font>**
<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/65113888/1776568514973-282a274e-f325-4fab-b0ed-16da4c55004c.png)

### **<font style="color:rgb(31, 35, 40);">Hackbar</font>**
<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/65113888/1776569711628-7053ad09-137d-45fa-ab0d-48337d959a31.png)

### **<font style="color:rgb(31, 35, 40);">Burp Suite</font>**<font style="color:rgb(31, 35, 40);"> </font>**<font style="color:rgb(31, 35, 40);">/Yakit</font>**
### **<font style="color:rgb(31, 35, 40);">dirsearch</font>**
<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/65113888/1776585960958-06f8ee6b-e49a-4a20-87bc-367abb5b3ba6.png)

## 解题
### [SWPUCTF 2021 新生赛]gift_F12
ID:mnivjk

方向：web

日期：2026-4-19

来源：NSSCTF

题目链接：[<font style="color:rgb(9, 105, 218);">[SWPUCTF 2021 新生赛]gift_F12</font>](https://www.nssctf.cn/problem/382)

解题过程：按F12  打开开发者工具，在源代码里面即可看到flag

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/65113888/1776589425600-c013a8cf-4c4c-466c-b151-6eec34ce77f3.png)

### [qsnctf-NO.0902]robots.txt
ID:mnivjk

方向：web

日期：2026-4-19

来源：QSNCTF

题目链接：[<font style="color:rgb(9, 105, 218);">[qsnctf-NO.0902]robots.txt</font>](https://www.qsnctf.com/#/main/driving-range?page=1&category=&difficulty=&keyword=robots.txt)

解题过程：

1.进入界面

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/65113888/1776590150420-d96814ef-b989-45e1-a85a-f719db671dd9.png)

2.在网址后加上<font style="color:rgb(31, 35, 40);">/robots.txt</font>

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/65113888/1776590204364-5ae35362-eb66-45c8-ba43-efeb17b1efed.png)

3.进入第三行的网址，获取用户名和密码

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/65113888/1776590261938-f5c12566-0a8f-455d-9898-01a5c8977d1e.png)

4.最后登录即可获得flag

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/65113888/1776590301157-209a740c-0961-4c0b-9519-72e429dbdf9e.png)

### [MoeCTF 2021]Web 安全入门指北—GET
ID:mnivjk

方向：web

日期：2026-4-19

来源：NSSCTF

题目链接：[<font style="color:rgb(9, 105, 218);">[MoeCTF 2021]Web 安全入门指北—GET</font>](https://www.nssctf.cn/problem/3412)

解题过程：

1.进入代码界面，用ai分析代码段含义

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/65113888/1776591275194-10005135-af41-47e2-bcd0-3d3b739e09d5.png)

2.在网址后加上/?moe=flag，进入即可查看flag

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/65113888/1776591376410-ac36aac0-222c-4402-ab87-20f1dd52fcd7.png)

# <font style="color:rgb(31, 35, 40);">Linux 理论基础</font>
### 环境搭建
之前已搭建过

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/65113888/1776593710987-47617bb3-2ac9-4845-b3cf-0135421452c9.png)

### 基础知识学习
#### 1.什么是Linux
+ Linux系统内核指的是由Linus Torvalds负责维护，提供硬件抽象层、硬盘及文件系统控制及多任务功能的系统核心程序。
+ Linux发行套件系统是我们常说的 Linux操作系统，也即是由 Linux内核与各种常用软件的集合产品。

#### 2.Shell
1. Shell是一个程序，提供一个与用户对话的环境。这个环境只有一个命令提示符，让用户从键盘输入命令，所以又称为命令行环境（command line interface，简写为CLI）。Shell 接收到用户输入的命令，将命令送入操作系统执行，并将结果返回给用户。
2. Shell是一个命令解释器，解释用户输入的命令。它支持变量、条件判断、循环操作等语法，所以用户可以用Shell命令写出各种小程序，又称为Shell脚本。这些脚本都通过Shell的解释执行，而不通过编译。
3. Shell是一个工具箱，提供了各种小工具，供用户方便地使用操作系统的功能。

#### 3.命令
进入命令行环境以后，用户会看到Shell的提示符。提示符往往是一串前缀，最后以一个美元符号$ 结尾，用户可以在这个符号后面输入各种命令。

<font style="color:rgb(77, 77, 77);">执行一个简单的命令pwd：</font>

```plain
[root@iZm5e8dsxce9ufaic7hi3uZ ~]# pwd  
/root

```

+ root：表示用户名；
+ iZm5e8dsxce9ufaic7hi3uZ：表示主机名；
+ ~：表示目前所在目录为家目录，其中root用户的家目录是 /root普通用户的家目录在 /home 下；
+ #：指示你所具有的权限（root用户为# ，普通用户为$ ）。
+ 执行whoami命令可以查看当前用户名
+ 执行hostname命令可以查看当前主机名；

#### 长短参数
<font style="color:rgb(0, 0, 0);background-color:rgb(250, 250, 250);">单个参数：ls -a（a 是英文 all 的缩写，表示“全部”） </font>

<font style="color:rgb(0, 0, 0);background-color:rgb(250, 250, 250);">多个参数：ls -al（全部文件 + 列表形式展示） </font>

<font style="color:rgb(0, 0, 0);background-color:rgb(250, 250, 250);">单个长参数：ls --all </font>

<font style="color:rgb(0, 0, 0);background-color:rgb(250, 250, 250);">多个长参数：ls --reverse --all </font>

<font style="color:rgb(0, 0, 0);background-color:rgb(250, 250, 250);">长短混合参数：ls --all -l </font>

#### <font style="color:rgb(0, 0, 0);background-color:rgb(250, 250, 250);">参数值</font>
<font style="color:rgb(0, 0, 0);background-color:rgb(250, 250, 250);">短参数：command -p 10（例如：ssh root@121.42.11.34 -p 22） </font>

<font style="color:rgb(0, 0, 0);background-color:rgb(250, 250, 250);">长参数：command --paramters=10（例如：ssh root@121.42.11.34 --port=22） </font>

#### <font style="color:rgb(0, 0, 0);background-color:rgb(250, 250, 250);">文件和目录</font>
`pwd`：查看当前目录路径

`ls`：列出文件和目录

+ `<font style="background-color:rgb(249, 242, 244);">-a</font>`显示所有文件和目录包括隐藏的
+ `<font style="background-color:rgb(249, 242, 244);">-l</font>`显示详细列表
+ `<font style="background-color:rgb(249, 242, 244);">-h</font>`适合人类阅读的
+ `<font style="background-color:rgb(249, 242, 244);">-t</font>`按文件最近一次修改时间排序
+ `<font style="background-color:rgb(249, 242, 244);">-i</font>`显示文件的`<font style="background-color:rgb(249, 242, 244);">inode</font>`（`<font style="background-color:rgb(249, 242, 244);">inode</font>`是文件内容的标识）

`cd`：切换目录

#### 浏览和创建文件
`cat`：一次性显示文件所有内容

`n`：显示行号

`touch`：创建一个文件

#### 文件的复制和移动
`cp`：拷贝文件和目录

`mv`：移动或重命名文件或目录

`rm`：删除文件和目录

#### 用户与权限
Linux是一个多用户的操作系统。在 Linux中，理论上来说，我们可以创建无数个用户，但是这些用户是被划分到不同的群组里面的，有一个用户，名叫 root，是一个很特殊的用户，它是超级用户，拥有最高权限。

`sudo`：以root身份运行命令

`useradd`：添加新用户

`passwd`：修改用户密码

#### 文件权限管理
`chmod`：修改访问权限

#### 软件仓库
Linux 下软件是以包的形式存在，一个软件包其实就是软件的所有文件的压缩包，是二进制的形式，包含了安装软件的所有指令。Red Hat 家族的软件包后缀名一般为 .rpm ， Debian 家族的软件包后缀是 .deb 。

Linux 的包都存在一个仓库，叫做软件仓库，它可以使用 yum 来管理软件包， yum 是 CentOS 中默认的包管理工具，适用于 Red Hat 一族。可以理解成 Node.js 的 npm 。



`yum update | yum upgrade` ：更新软件包

`yum search xxx`：搜索相应的软件包

`yum install xxx`安装软件包

`yum remove xxx`删除软件包

<font style="color:rgb(0, 0, 0);background-color:rgb(250, 250, 250);"></font>

#### <font style="color:rgb(0, 0, 0);background-color:rgb(250, 250, 250);">切换CentOS软件源</font>
#### 阅读手册
man手册种类：

1.可执行程序或Shell命令；

2.系统调用（ Linux 内核提供的函数）；

3.库调用（程序库中的函数）；

4.文件（例如/etc/passwd）；

5.特殊文件（通常在/dev下）；

6.游戏；

7.杂项（man(7)，groff(7)）；

8.系统管理命令（通常只能被root用户使用）；

9.内核子程序。

#### help
man 命令像新华词典一样可以查询到命令或函数的详细信息，但其实我们还有更加快捷的方式去查询，command --help或command -h，它没有 man 命令显示的那么详细，但是它更加易于阅读。

#### 文本操作
`grep`：<font style="color:rgb(77, 77, 77);">在文件中查找关键字，并显示关键字所在行。</font>

`-i`：忽略大小写，grep -i path /etc/profile

`-n`：显示行号，grep -i path /etc/profile

`-v`：只显示搜索文本不在的那些行，grep -v path /etc/profile

`-r`：递归查找，grep -r hello /etc，Linux 中还有一个 rgrep 命令，作用相当于grep -r

`sort`：<font style="color:rgb(77, 77, 77);">对文件的行进行排序。</font>

`-o`：将排序后的文件写入新文件，sort -o name_sorted.txt name.txt；

`-r`：倒序排序，sort -r name.txt ；

`-R`：随机排序，sort -R name.txt ；

`-n`：对数字进行排序，默认是把数字识别成字符串的，因此 138 会排在 25 前面，如果添加了 -n 数字排序的话，则 25 会在 138 前面。

`wc`：word count的缩写，<font style="color:rgb(77, 77, 77);">用于文件的统计。它可以统计单词数目、行数、字符数，字节数等。</font>







<font style="color:rgb(77, 77, 77);"></font>

<font style="color:rgb(77, 77, 77);"></font>

