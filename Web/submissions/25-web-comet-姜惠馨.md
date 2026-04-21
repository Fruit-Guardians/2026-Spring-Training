# 工具安装
## 浏览器开发者工具F12
在网页点击F12即可找到并使用<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/67411697/1776151510727-fe033e7c-9b81-428a-bd55-bb4d63ca1564.png)

## Hackbar浏览器插件
在火狐浏览器进行下载并使用

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/67411697/1776151034497-75ee9392-3f37-4f30-819c-e4933a80db3c.png)<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/67411697/1776151047169-deffb9ae-a22b-4612-82f8-b988b78c6ceb.png)

## Yakit
在Yakit官网进行下载并使用<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/67411697/1776151140606-2cbd794c-042b-4052-832f-c5bef058075b.png)<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/67411697/1776151151846-92fbee28-ef44-44be-987e-0949c8f0871f.png)

## AI
网页版豆包、deepseek等AI工具

## diesearch
先下载python3.14后，在cmd用指令代码下载diesearch

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/67411697/1776151379737-0fa8b491-c734-412a-8a38-6bdf9ff80b41.png)<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/67411697/1776151404343-e11be1e3-2cb7-4fd5-b041-e5f5c776fd18.png)<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/67411697/1776151412250-8ac4fec1-b644-4ca5-a0ae-1df9a5428be5.png)<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/67411697/1776151430456-d18fece7-17e4-4068-8751-cccfc4ed725d.png)

## Linux
下载 VMware Workstation Pro 和 Ubuntu 镜像文件后，在 VMware 中创建 Ubuntu 虚拟机， 启动虚拟机并安装 Ubuntu 系统和 VMware Tools 。 

# writeup
+ ID：comet
+ 方向：web

## 题目1
+ 题目名称： [SWPUCTF 2021 新生赛]gift_F12  
+ <font style="color:#000000;">题目链接：</font>[<font style="color:rgb(9, 105, 218);">[SWPUCTF 2021 新生赛]gift_F12</font>](https://www.nssctf.cn/problem/382)<font style="color:rgb(31, 35, 40);"> </font>
+ <font style="color:rgb(31, 35, 40);">日期：2026年4月12日</font>

### 环境搭建
+ 操作系统：windows
+ 工具与版本：浏览器开发者工具F12

### 解题过程
1. 点击题目链接并进入环境。
2. 按F12，并按ctrl+U查看源代码，按ctrl+F进行全局搜索，搜索关键词flag，即可定位到flag的位置：<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/67411697/1775965315169-ca4a90d9-e68d-4cc8-abba-35ef31fd8d01.png)
3. 按照题目要求的格式将"WLLMCTF"改为"NSSCTF"再提交答案即可。

## 题目2
+ 题目链接：[<font style="background-color:rgb(13, 17, 23);">[qsnctf-NO.0902]robots.txt</font>](https://www.qsnctf.com/#/main/driving-range?page=1&category=&difficulty=&keyword=robots.txt)
+ 日期：2026年4月12日

### 环境搭建
+ 操作系统：windows
+ 工具与版本：浏览器开发者工具F12

### 解题过程
1. 点击题目链接并进入环境。
2. 根据指引，在原环境链接后加上/robots.txt，得到3个文件名：

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/67411697/1775973079609-f87764d3-416f-4909-ac07-8ae214a89931.png)

3. 访问第三个secret.php，得到账户名和密码：

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/67411697/1775973160341-3b206527-2f1d-4b27-a9e0-311dc774c8d3.png)

4. 回到原界面，输入账户名和密码得到flag：

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/67411697/1775973203951-3d724997-1103-4759-85c6-d826ea3ccee2.png)

5. 提交flag即可。

## 题目3
+ 题目链接：[<font style="background-color:rgb(13, 17, 23);">[MoeCTF 2021]Web 安全入门指北—GET</font>](https://www.nssctf.cn/problem/3412)
+ 日期：2026年4月12日

### 环境搭建
+ 操作系统：windows

### 解题过程
1. 点击题目链接并进入环境：

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/67411697/1775974617752-2b1574ae-51eb-4910-82e4-593257d4ec93.png)

2. 学习GET和POST请求的相关知识，并让ai简单分析如上代码。
3. 得知该代码是典型的GET请求，可以直接在地址栏后加上？moe=flag，回车得到flag：

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/67411697/1775974838907-5a3f727e-d23c-40a1-ac5b-dbd7fb3a2eaa.png)

4. 提交flag即可。

# Linux学习笔记
## **<font style="color:rgb(77, 77, 77);">什么是 Linux</font>**
真正的Linux指的是系统内核，而我们常说的Linux指的是 “发行版完整的包含一些基础软件的操作系统”。

## shell
Shell这个单词的原意是 “外壳”，跟kernel（内核）相对应，比喻内核外面的一层，即用户跟内核交互的对话界面。

1. Shell是一个程序，提供一个与用户对话的环境。这个环境只有一个命令提示符，让用户从键盘输入命令，所以又称为命令行环境（command line interface，简写为CLI）。Shell 接收到用户输入的命令，将命令送入操作系统执行，并将结果返回给用户。
2. Shell是一个命令解释器，解释用户输入的命令。它支持变量、条件判断、循环操作等语法，所以用户可以用Shell命令写出各种小程序，又称为Shell脚本。这些脚本都通过Shell的解释执行，而不通过编译。
3. Shell是一个工具箱，提供了各种小工具，供用户方便地使用操作系统的功能。

Shell有很多种，只要能给用户提供命令行环境的程序，都可以看作是 Shell。

## 命令
进入命令行环境以后，用户会看到Shell的提示符。提示符往往是一串前缀，最后以一个美元符号$ 结尾，用户可以在这个符号后面输入各种命令。

###  命令行提示符  
 [root@主机名 ~]#  ：root（超级用户）、~（家目录）、#（管理员权限）；普通用户为  $  。  

###   命令格式
短参数：ls-a；长参数：ls--all；带值参数：ssh-p 22 root@ip。

## 文件与目录操作
### 系统核心目录
+ <font style="color:#000000;background-color:rgba(0, 0, 0, 0);">/：根目录（唯一）；</font>`<font style="color:#000000;background-color:rgba(0, 0, 0, 0);">/home</font>`<font style="color:#000000;background-color:rgba(0, 0, 0, 0);">：普通用户家目录；</font>`<font style="color:#000000;background-color:rgba(0, 0, 0, 0);">/root</font>`<font style="color:#000000;background-color:rgba(0, 0, 0, 0);">：管理员家目录。</font>
+ `<font style="color:#000000;background-color:rgba(0, 0, 0, 0);">/etc</font>`<font style="color:#000000;background-color:rgba(0, 0, 0, 0);">：配置文件；</font>`<font style="color:#000000;background-color:rgba(0, 0, 0, 0);">/bin</font>`<font style="color:#000000;background-color:rgba(0, 0, 0, 0);">：可执行程序；</font>`<font style="color:#000000;background-color:rgba(0, 0, 0, 0);">/tmp</font>`<font style="color:#000000;background-color:rgba(0, 0, 0, 0);">：临时文件；</font>`<font style="color:#000000;background-color:rgba(0, 0, 0, 0);">/usr</font>`<font style="color:#000000;background-color:rgba(0, 0, 0, 0);">：用户程序。</font>

### 文件链接
+ **<font style="color:#000000;background-color:rgba(0, 0, 0, 0);">硬链接</font>**<font style="color:#000000;background-color:rgba(0, 0, 0, 0);">：</font>`<font style="color:#000000;background-color:rgba(0, 0, 0, 0);">ln file1 file2</font>`<font style="color:#000000;background-color:rgba(0, 0, 0, 0);">，共享 inode，只能链接文件，删除原文件不影响。</font>
+ **<font style="color:#000000;background-color:rgba(0, 0, 0, 0);">软链接</font>**<font style="color:#000000;background-color:rgba(0, 0, 0, 0);">：</font>`<font style="color:#000000;background-color:rgba(0, 0, 0, 0);">ln -s file1 file2</font>`<font style="color:#000000;background-color:rgba(0, 0, 0, 0);">，类似快捷方式，可链接目录，原文件删除失效。</font>

## 用户权限与管理
### 用户管理
+ `<font style="background-color:rgba(0, 0, 0, 0);">root</font>`<font style="background-color:rgba(0, 0, 0, 0);">：超级用户，最高权限；普通用户权限受限。</font>
+ <font style="background-color:rgba(0, 0, 0, 0);">命令：</font>`<font style="background-color:rgba(0, 0, 0, 0);">useradd</font>`<font style="background-color:rgba(0, 0, 0, 0);">（创建）、</font>`<font style="background-color:rgba(0, 0, 0, 0);">passwd</font>`<font style="background-color:rgba(0, 0, 0, 0);">（设密码）、</font>`<font style="background-color:rgba(0, 0, 0, 0);">userdel -r</font>`<font style="background-color:rgba(0, 0, 0, 0);">（删除 + 家目录）、</font>`<font style="background-color:rgba(0, 0, 0, 0);">su</font>`<font style="background-color:rgba(0, 0, 0, 0);">（切换用户）、</font>`<font style="background-color:rgba(0, 0, 0, 0);">sudo</font>`<font style="background-color:rgba(0, 0, 0, 0);">（临时提权）。</font>

### 群组管理
`<font style="background-color:rgba(0, 0, 0, 0);">groupadd</font>`（创建）、`<font style="background-color:rgba(0, 0, 0, 0);">groupdel</font>`（删除）、`<font style="background-color:rgba(0, 0, 0, 0);">groups</font>`（查看群组）、`<font style="background-color:rgba(0, 0, 0, 0);">usermod -g</font>`（改主群组）。  

## 网络与远程
### SSH远程连接
+ <font style="color:#000000;background-color:rgba(0, 0, 0, 0);">登录：</font>`<font style="color:#000000;background-color:rgba(0, 0, 0, 0);">ssh 用户名@IP</font>`<font style="color:#000000;background-color:rgba(0, 0, 0, 0);">。</font>
+ <font style="color:#000000;background-color:rgba(0, 0, 0, 0);">免密登录：</font>`<font style="color:#000000;background-color:rgba(0, 0, 0, 0);">ssh-keygen</font>`<font style="color:#000000;background-color:rgba(0, 0, 0, 0);"> 生成密钥对 → </font>`<font style="color:#000000;background-color:rgba(0, 0, 0, 0);">ssh-copy-id 用户名@IP</font>`<font style="color:#000000;background-color:rgba(0, 0, 0, 0);"> 上传公钥。</font>
+ <font style="color:#000000;background-color:rgba(0, 0, 0, 0);">别名登录：配置 </font>`<font style="color:#000000;background-color:rgba(0, 0, 0, 0);">~/.ssh/config</font>`<font style="color:#000000;background-color:rgba(0, 0, 0, 0);">，简化登录命令。</font>

### 文件传输
`<font style="color:#000000;background-color:rgba(0, 0, 0, 0);">scp</font>`<font style="color:#000000;">：安全拷贝文件；</font>`<font style="color:#000000;background-color:rgba(0, 0, 0, 0);">rsync</font>`<font style="color:#000000;">：增量同步文件。  </font>

## <font style="color:#000000;">Vim编辑器</font>
### 三种模式
+ **<font style="color:#000000;background-color:rgba(0, 0, 0, 0);">交互模式</font>**<font style="color:#000000;background-color:rgba(0, 0, 0, 0);">：默认模式，移动光标、复制 / 删除 / 撤销（</font>`<font style="color:#000000;background-color:rgba(0, 0, 0, 0);">dd</font>`<font style="color:#000000;background-color:rgba(0, 0, 0, 0);">删行、</font>`<font style="color:#000000;background-color:rgba(0, 0, 0, 0);">yy</font>`<font style="color:#000000;background-color:rgba(0, 0, 0, 0);">复制、</font>`<font style="color:#000000;background-color:rgba(0, 0, 0, 0);">u</font>`<font style="color:#000000;background-color:rgba(0, 0, 0, 0);">撤销）。</font>
+ **<font style="color:#000000;background-color:rgba(0, 0, 0, 0);">插入模式</font>**<font style="color:#000000;background-color:rgba(0, 0, 0, 0);">：按</font>`<font style="color:#000000;background-color:rgba(0, 0, 0, 0);">i/a/o</font>`<font style="color:#000000;background-color:rgba(0, 0, 0, 0);">进入，编辑文本，</font>`<font style="color:#000000;background-color:rgba(0, 0, 0, 0);">Esc</font>`<font style="color:#000000;background-color:rgba(0, 0, 0, 0);">退出。</font>
+ **<font style="color:#000000;background-color:rgba(0, 0, 0, 0);">命令模式</font>**<font style="color:#000000;background-color:rgba(0, 0, 0, 0);">：按</font>`<font style="color:#000000;background-color:rgba(0, 0, 0, 0);">:</font>`<font style="color:#000000;background-color:rgba(0, 0, 0, 0);">进入，</font>`<font style="color:#000000;background-color:rgba(0, 0, 0, 0);">:wq</font>`<font style="color:#000000;background-color:rgba(0, 0, 0, 0);">保存退出、</font>`<font style="color:#000000;background-color:rgba(0, 0, 0, 0);">:q!</font>`<font style="color:#000000;background-color:rgba(0, 0, 0, 0);">强制退出、</font>`<font style="color:#000000;background-color:rgba(0, 0, 0, 0);">set nu</font>`<font style="color:#000000;background-color:rgba(0, 0, 0, 0);">显示行号。</font>

### 常用操作
+ <font style="color:#000000;background-color:rgba(0, 0, 0, 0);">查找：</font>`<font style="color:#000000;background-color:rgba(0, 0, 0, 0);">/关键词</font>`<font style="color:#000000;background-color:rgba(0, 0, 0, 0);">，n 下一个、N 上一个。</font>
+ <font style="color:#000000;background-color:rgba(0, 0, 0, 0);">替换：</font>`<font style="color:#000000;background-color:rgba(0, 0, 0, 0);">:%s/旧/新/g</font>`<font style="color:#000000;background-color:rgba(0, 0, 0, 0);">（全文替换）。</font>
+ <font style="color:#000000;background-color:rgba(0, 0, 0, 0);">分屏：</font>`<font style="color:#000000;background-color:rgba(0, 0, 0, 0);">:sp</font>`<font style="color:#000000;background-color:rgba(0, 0, 0, 0);">横向、</font>`<font style="color:#000000;background-color:rgba(0, 0, 0, 0);">:vsp</font>`<font style="color:#000000;background-color:rgba(0, 0, 0, 0);">垂直。</font>

