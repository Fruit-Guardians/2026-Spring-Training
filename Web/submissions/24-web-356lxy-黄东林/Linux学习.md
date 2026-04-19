
# linux学习
## linux种类
- RHEL(收费)
- Fedora(RHEL免费版)
- CentOS(免费)
- Deepin(中国发行)
- Debian(免费且外国流行)
- Ubuntu(非常流行)
## linux命令
### 快捷方式
- 通过上下方向键 ↑ ↓ 来调取过往执行过的Linux命令；

- 命令或参数仅需输入前几位就可以用 Tab 键补全；

- Ctrl + R ：用于查找使用过的命令（history命令用于列出之前使用过的所有命令，然后输入!命令加上编号 (!2) 就可以直接执行该历史命令）；

- Ctrl + L：清除屏幕并将当前行移到页面顶部；

- Ctrl + C：中止当前正在执行的命令；

- Ctrl + U：从光标位置剪切到行首；

- Ctrl + K：从光标位置剪切到行尾；

- Ctrl + W：剪切光标左侧的一个单词；

- Ctrl + Y：粘贴Ctrl + U | K | Y剪切的命令；

- Ctrl + A：光标跳到命令行的开头；

- Ctrl + E：光标跳到命令行的结尾；

- Ctrl + D：关闭Shell会话；
## 常用命令
**pwd**:显示当前目录的路径  
**which**：查看命令的可执行文件所在路径  
**ls**:列出文件和目录wwww（-a ,-l,-t,-h,-i）  
**cd****:切换目录  
>cd / --> 跳转到根目录  
cd ~ --> 跳转到家目录  
cd .. --> 跳转到上级目录  
cd ./home --> 跳转到当前目录的home目录下  
cd /home/lion --> 跳转到根目录下的home目录下的lion目录  
cd --> 不添加任何参数，也是回到家目录  

**du**:列举目录大小信息。(-h,-a,-s)  
**cat**：一次性显示文件所有内容，更适合查看小的文件。-n 显示行号  
**less**：分页显示文件内容，更适合查看大的文件。-n 显示行号   
>【快捷操作】查看文件内容

    空格键：前进一页（一个屏幕）；

    b 键：后退一页；

    回车键：前进一行；

    y 键：后退一行；

    上下键：回退或前进一行；

    d 键：前进半页；

    u 键：后退半页；

    q 键：停止读取文件，中止less命令；

    = 键：显示当前页面的内容是文件中的第几行到第几行以及一些其它关于本页内容的详细信息；

    h 键：显示帮助文档；

    / 键：进入搜索模式后，按 n 键跳到一个符合项目，按 N 键跳到上一个符合项目，同时也可以输入正则表达式匹配。  
**head**：显示文件的开头几行（10，-n指定）  
**tail**：显示文件的结尾几行（10，-n指定）  
 **touch**：创建一个文件  
**mkdir**：创建一个目录（-p递归）  
**cp**：拷贝文件和目录
>cp file file_copy --> file 是目标文件，file_copy 是拷贝出来的文件  
cp file one --> 把 file 文件拷贝到 one 目录下，并且文件名依然为 file  
cp file one/file_copy --> 把 file 文件拷贝到 one 目录下，文件名为file_copy  
cp *.txt folder --> 把当前目录下所有 txt 文件拷贝到 folder 目录下  

**mv**：移动（重命名）文件或目录，与 cp 命令用法相似。  
**rm**：删除文件和目录 (-i确认，-f强制，-r递归删除目录，（rm -rf常见）)
>rm new_file  --> 删除 new_file 文件  
 rm f1 f2 f3  --> 同时删除 f1 f2 f3 3个文件  

**ln**：创建链接(无参数：硬链接；-s：软链接)
>软链接相当于快捷方式，若删除了本体则软链接也会消失。  
>硬链接则相反，本体或链接删除都不会对另一方造成影响。
![](assets/2026-04-11-13-54-42.png)  
## 用户与权限  
Linux是一个多用户的操作系统。在 Linux中，理论上来说，我们可以创建无数个**用户**，但是这些用户是被划分到不同的**群组**里面的，有一个用户，名叫 **root**，是一个很特殊的用户，它是超级用户，拥有最高权限。  

**sudo**：以 root身份运行命令  
**useradd**：添加新用户  
**passwd**：修改用户密码  
**userdel**:删除用户  
**su**：切换用户  
> 以上4个命令都需要root权限  

**groupadd**：创建群组  
**groupdel**：删除一个已存在的群组  
**groups**：查看用户所在群组  
>groups lion  --> 查看 lion 用户所在的群组    

**usermod**：用于修改用户的账户（-l 用户重命名,-g 修改用户所在的群组，-G 一次性让用户添加多个群组，-a 在使用-G时追加自动离开的原群组）  
**chgrp**：用于修改文件的群组  
>chgrp bar file.txt --> file.txt文件的群组修改为bar    

**chown**：改变文件的所有者，需要 root 身份才能运行(-R 递归设置子目录和子文件) 
>chown lion file.txt --> 把其它用户创建的file.txt转让给lion用户  
chown lion:bar file.txt --> 把file.txt的用户改为lion，群组改为bar    

**chmod**：修改访问权限。(-R 递归修改权限)
>chmod 740 file.txt   
chmod -R 777 /home/lion 

### 权限  

>d ：表示目录，就是说这是一个目录，普通文件是 - ，链接是 l 。  
r (4)：read表示文件可读。  
w (2)：write表示文件可写，一般有写的权限，就有删除的权限。  
x (1)：execute表示文件可执行。   
\- ：表示没有相应权限。  

>改变权限只需做一些加法就行  

**drwxr-xr-x**的意思?  
>- 它是一个文件夹；  
>- 它的所有者具有：读、写、执行权限；  
>- 它的群组用户具有：读、执行的权限，没有写的权限；  
>- 它的其它用户具有：读、执行的权限，没有写的权限。   

**字母分配权限**  
u：user 的缩写，用户的意思，表示所有者。

g ：group 的缩写，群组的意思，表示群组用户。

o ：other 的缩写，其它的意思，表示其它用户。

a ：all 的缩写，所有的意思，表示所有用户。

\+ ：加号，表示添加权限。

\- ：减号，表示去除权限。

= ：等于号，表示分配权限。
>1. chmod u+rx file --> 文件file的所有者增加读和运行的权限  
>2. chmod g+r file --> 文件file的群组用户增加读的权限  
>3. chmod o-r file --> 文件file的其它用户移除读的权限  
>4. chmod g+r o-r file --> 文件file的群组用户增加读的权限，其它用户移除读的权限  
>5. chmod go-r file --> 文件file的群组和其他用户移除读的权限  
>6. chmod +x file --> 文件file的所有用户增加运行的权限  
>7. chmod u=rwx,g=r,o=- file --> 文件file的所有者分配读写和执行的权限，群组其它用户分配读的权限，其他用户没有任何权限    

**locate**：搜索包含关键字的所有文件和目录
> 注意：locate 命令会去文件数据库中查找命令，而不是全磁盘查找，因此刚创建的文件并不会更新到数据库中，所以无法被查找到，可以执行 updatedb 命令去更新数据库。 

**find**：用于查找文件
>find -name "file.txt" --> 当前目录以及子目录下通过名称查找文件    
find -name "*.txt" -atime -7  --> 近 7天内访问过的.txt结尾的文件  
find . -name "file" -type f  --> 只查找当前目录下的file文件  
find . -name "file" -type d  --> 只查找当前目录下的file目录  
find -name "*.txt" -printf "%p - %u\n" --> 找出所有后缀为txt的文件，并按照 %p - %u\n 格式打印，其中%p=文件名，%u=文件所有者  
find -name "*.jpg" -delete --> 删除当前目录以及子目录下所有.jpg为后缀的文件，不会有删除提示，因此要慎用  
find -name "*.c" -exec chmod 600 {} \; --> 对每个.c结尾的文件，都进行 -exec 参数指定的操作，{} 会被查找到的文件替代，\; 是必须的结尾  
find -name "*.c" -ok chmod 600 {} \; --> 和上面的功能一样，会多一个确认提示  


>注意：find 命令只会查找完全符合 “何物” 字符串的文件，而 locate 会查找所有包含关键字的文件

## 软件仓库  
**yum** 常用命令 （**kail**无yum，但有apt与yum类似）
>- yum update | yum upgrade 更新软件包  
>- yum search xxx 搜索相应的软件包  
>- yum install xxx安装软件包  
>- yum remove xxx删除软件包   

## 阅读手册  
**man**    
**help**
### man手册种类
1. 可执行程序或Shell命令；

2. 系统调用（ Linux 内核提供的函数）；

3. 库调用（程序库中的函数）；

4. 文件（例如/etc/passwd）；

5. 特殊文件（通常在/dev下）；

6. 游戏；
 
7. 杂项（man(7)，groff(7)）；

8. 系统管理命令（通常只能被root用户使用）；

9. 内核子程序。  
>man 3 rand  --> 表示在手册的第三部分查找 rand 函数  
man ls    --> 查找 ls 用法手册   
# linux进阶  
## 文本操作  
**grep**：全局搜索一个正则表达式，并且打印到屏幕。（找关键字） （-i 忽略大小写，-n 显示行号，-v 反向搜索，-r 递归）  
 >grep可以配合正则表达式使用  
 >>grep -E path /etc/profile --> 完全匹配path  
grep -E ^path /etc/profile --> 匹配path开头的字符串  
grep -E [Pp]ath /etc/profile --> 匹配path或Path   

**sort**:对文件的行进行排序
>- -o将排序后的文件写入新文件，sort -o name_sorted.txt name.  txt；
>- -r倒序排序，sort -r name.txt ；  
>- -R随机排序，sort -R name.txt ；  
>- -n对数字进行排序，默认是把数字识别成字符串的，因此 138 会排在 25 前面，如果添加了 -n 数字排序的话，则 25 会在 138 前面。 

**wc**:word count的缩写，用于文件的统计  (行数,单词数，字节数)
>-l只统计行数， wc -l name.txt；  
-w只统计单词数，wc -w name.txt；  
-c只统计字节数，wc -c name.txt；  
-m只统计字符数，wc -m name.txt。  

**uniq**:删除文件中的重复内容。(-c统计重复行数，-d只显示重复的行数)  
>【注意】它只能去除连续重复的行数。(不会对实际文本作出修改，若两个重复行中间有未重复行则会重新运行)  

**cut**：剪切文件的一部分内容
>-d用于指定用什么分隔符（比如逗号、分号、双引号等）  
-f表示剪切下用分隔符分割的哪一块或哪几块区域  
>>cut -d , -f 3 1.txt    

## 重定向 管道 流  
在 Linux 中一个命令的去向可以有 3 个地方：终端、文件、作为另外一个命令的入参。  


- 标准输入stdin，终端接收键盘输入的命令，会产生两种输出；

- 标准输出stdout，终端输出的信息（不包含错误信息）；

- 标准错误输出stderr ，终端输出的错误信息。  
### 重定向  
把本来要显示在终端的命令结果，输送到别的地方（到文件中或者作为其他命令的输入）。   

- 输出重定向 >(覆盖原文件)  
- 输出重定向 >>(追加文件的末尾)  
- 输出重定向 2>：标准错误输出  
>cat not_exist_file.csv > res.txt 2> errors.log    
- 输出重定向 2>>: 与>>类似  
- 输出重定向 2>&1:标准输出和标准错误输出都重定向都一个地方  
>cat not_exist_file.csv > res.txt 2>&1  # 覆盖输出  
cat not_exist_file.csv >> res.txt 2>&1 # 追加输出    
- 输入重定向 <：用于指定命令的输入。
>对于支持文件名参数的命令，加与不加<,两者结果类似  
>对于不支持文件名参数的命令，必须用<重定向，否则回一直等键盘输入  

- 输入重定向 <<：将键盘的输入重定向为某个命令的输入  
>sort -n << END # 输入这个命令之后，按下回车，终端就进入键盘输入模式，其中END为结束命令（这个可以自定义）   
### 管道  |    
把两个命令连起来使用，一个命令的输出作为另外一个命令的输入  
>cut -d , -f 1 name.csv | sort > sorted_name.txt   
grep log -Ir /var/log | cut -d : -f 1 | sort | uniq   

### 流  
流并非一个命令，流就是读一点数据, 处理一点点数据。其中数据一般就是二进制格式。上面提及的重定向或管道，就是把数据当做流去运转的。  
## 进程  
### 查看进程  
**w**：帮助我们快速了解系统中目前有哪些用户登录着，以及他们在干什么  
**ps**:用于显示当前系统中的进程， ps 命令显示的进程列表不会随时间而更新，是静态的，是运行 ps 命令那个时刻的状态或者说是一个进程快照。  
**top**: 获取进程的动态列表  
**kill**: 结束一个进程，kill+PID  
>kill 956 # 结束进程号为956的进程  
kill 956 957 # 结束多个进程  
kill -9 7291 # 强制结束进程    
### 管理进程  
进程状态  
1. 状态码 R ：表示正在运行的状态；

2. 状态码 S ：表示中断（休眠中，受阻，当某个条件形成后或接受到信号时，则脱离该状态）；

3. 状态码 D ：表示不可中断（进程不响应系统异步信号，即使用 kill 命令也不能使其中断）；

4. 状态码 Z ：表示僵死（进程已终止，但进程描述符依然存在，直到父进程调用 wait4() 系统函数后将进程释放）；

5. 状态码 T ：表示停止（进程收到 SIGSTOP 、 SIGSTP 、 SIGTIN 、 SIGTOU 等停止信号后停止运行）。  

前台进程&后台进程  
- **&** （在命令末尾加&）启动后台进程，它的缺点是后台进程与终端相关联，一旦关闭终端，进程就自动结束了  
- **nohup**：使进程不受挂断（关闭终端等动作）的影响
>cp name.csv name-copy.csv &   
nohup cp name.csv name-copy.csv    
nohup cp name.csv name-copy.csv &  

- **bg**:使一个 “后台暂停运行” 的进程，状态改为“后台运行”(不加参数的情况下默认作用与最近的一个后台程序)  
>前端开发时我们经常会执行 yarn start 启动项目  
此时我们执行 ctrl + z 先使其暂停  
然后执行 bg 使其转为后台运行  
这样当前终端就空闲出来可以干其它事情了，如果想要唤醒它就使用 fg 命令即可（后面会讲）    

- **jobs**:显示当前终端后台进程状态。  
- **fg**:使进程转为前台运行，用法和 bg 命令类似  
### 守护进程  
在 Linux 中有些进程是特殊的，它不与任何进程关联，不论用户的身份如何，都在后台运行，这些进程的父进程是 PID 为 1 的进程， PID 为 1 的进程只在系统关闭时才会被销毁。它们会在后台一直运行等待分配工作。我们将这类进程称之为守护进程 daemon （最后有一个d，如systemd、httpd。）  
**systemd**  
>常用命令  
systemctl start nginx # 启动服务  
systemctl stop nginx # 停止服务  
systemctl restart nginx # 重启服务  
systemctl status nginx # 查看服务状态  
systemctl reload nginx # 重载配置文件(不停止服务的情况)  
systemctl enable nginx # 开机自动启动服务  
systemctl disable nginx # 开机不自动启动服务  
systemctl is-enabled nginx # 查看服务是否开机自动启动  
systemctl list-unit-files --type=service # 查看各个级别下服务的启动和禁用情况   

## 文件压缩解压  

- 打包：是将多个文件变成一个总的文件，它的学名叫存档、归档。

- 压缩：是将一个大文件（通常指归档）压缩变成一个小文件。  

**tar**：创建一个tar归档
>-cvf表示 create（创建）+ verbose（细节）+ file（文件），创建归档文件并显示操作细节；  
-tf 显示归档里的内容，并不解开归档；  
-rvf追加文件到归档，tar -rvf archive.tar file.txt；  
-xvf解开归档，tar -xvf archive.tar。    

**gzip/guzip**:“压缩 / 解压” 归档  
**zcat、zless、zmore**:查看压缩文件内容  
**zip/unzip**：“压缩 / 解压” zip 文件  
>unzip -l archive.zip # 不解开 .zip 文件，只看其中内容  
zip -r sort.zip sort/ # 将sort文件夹压缩为 sort.zip，其中-r表示递归    
##  编译安装  


1. 下载源代码  
去官网下载然后用**scp**同步到服务器  
或者直接用**wegt**下载   
>**scp**(备份)  
scp 文件名 用户名@服务器ip:目标路径 

>**wget**: 可以使我们直接从终端控制台下载文件，只需要给出文件的 HTTP 或 FTP 地址。  
wget [参数][URL地址] 

2. 解压压缩包  
解压后进入该文件目录

3.  配置  
执行./configure，它会分析你的电脑去确认编译所需的工具是否都已经安装了

4. 编译  
执行make命令

5. 安装  
执行make install命令，安装完成后执行ls /usr/local/bin/查看是否有安装  
##  网络  
**ifconfig**  :查看 ip 网络相关信息
>- eth0对应有线连接
>- lo表示本地回环  (127.0.0.1)
>- wlan0表示无线局域网  

**host**:  ip 地址和主机名的互相转换。  
**ssh**: 连接远程服务器(ssh 用户@ip:port )  
## 配置ssh  
config文件可以配置ssh，方便批量管理多个ssh连接。  
配置文件分为以下几种：  


- 全局ssh服务端的配置：/etc/ssh/sshd_config；

- 全局 ssh客户端的配置：/etc/ssh/ssh_config（很少修改）；

- 当前用户ssh客户端的配置：~/.ssh/config。（实现免密登录）  
>配置当前用户的config：
 >>#创建config  
vim ~/.ssh/config  
#填写一下内容  
Host lion # 别名  
    HostName 172.x.x.x # ip 地址  
  Port 22 # 端口  
  User root # 用户  
### 免密登录  
1. 运行ssh-keygen会在~/.ssh/目录下生成两个文件：  


- id_rsa.pub：公钥

- id_rsa：私钥  

2. 执行ssh-copy-id root@172.x.x.x（把客户机的公钥追加到服务器~/.ssh/authorized_keys的文件中）    
3. 最后运行ssh root@172.x.x.x就可以实现免密登录服务器了。  
配合上卖弄设置好的别名，直接执行ssh lion就可以登陆    

## 备份  
**scp**   

**rsync**：主要用于远程同步文件。它可以同步两个目录，不管它们是否处于同一台电脑。 

>-a保留文件的所有信息，包括权限，修改日期等；  
-r递归调用，表示子目录的所有文件也都包括；  
-v冗余模式，输出详细操作信息。  

>rsync -arv Images/ backups/ # 将Images 目录下的所有文件备份到 backups 目录下  
rsync -arv Images/ root@192.x.x.x:backups/ # 同步到服务器的backups目录下   

### 系统  
**halt**：关闭系统，需要 root 身份  
**reboot**：重启系统，需要root身份  
**poweroff**：关机，不需要root  

## vim  
运行vim file.name打开vim  
>1.保存并退出 :wq 或 :x ；  
2.不保存且退出 :q! 。


常用模式  

- 交互模式 
>- 查找（按 /）（n 下一个；N 上一个）  
>- 移动  （方向键）(跳至行首按数字**0**，跳至行末\$ )    
>- 剪切 dd(行) 2dd（多行） dw（一个单词） 2dw（多个单词） d0（从光标到行首） d$（从光标到行末）  
>- 复制 y 同剪切  
>- 粘贴 p  
>- 撤销 u  
>- 取消撤销 Ctrl + r  
>- 跳转指定行 数字+gg G(最后一行) gg(第一行)   



- 插入模式（按i进入）

- 命令模式（按 ：）  
>- 运行外部命令（:!）(在该文件所在的目录)  
>- 查找并替换（:s/one/two）末尾加g表示对行操作，%s表示全文替换  
>- 合并文件（:r）  
>- 分屏（:sp||:vsp）
>>分屏的快捷键：Ctrl+w再加"方向键"、+、-、=、r、q、o  

 

- 可视模式（按v(字符)，V(行)，ctrl+V(块)） 
>d键，表示删除选中；  
I键，表示在选中之前插入；  
u键，表示选中变为小写；  
U键，表示选中变为大写；  




 
