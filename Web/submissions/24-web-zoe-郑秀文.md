# web学习
## 安装工具
### 1.Hackbar 安装   
**参考博客** [harkbar教程](https://github.com/HCTYMFF/hackbar2.1.3)  
**直接在Google扩展中安装**  
![harkbar安装](https://cdn.jsdelivr.net/gh/zoe3971/my_images@main/harkbar1.png)  
![harkbar](https://cdn.jsdelivr.net/gh/zoe3971/my_images@main/harkbar2.png)
### 2.Burp suite安装  
**破解Burp suite**  
![Burp suite](https://cdn.jsdelivr.net/gh/zoe3971/my_images@main/破解打开burpsuite.png)  
**CA证书**  
![ca](https://cdn.jsdelivr.net/gh/zoe3971/my_images@main/burp-ca.png)  
### 3.dirsearch  
**参考博客**[dirsearch的安装(非常详细)和使用](https://blog.csdn.net/m0_73185293/article/details/131239309?sharetype=blog&shareId=131239309&sharerefer=APP&sharesource=2401_88034999&sharefrom=link)  
**先配置python3**  
![配置python3](https://cdn.jsdelivr.net/gh/zoe3971/my_images@main/配置python3.png)   
**下载dirsearch-master.zip文件**  
![dirsearch安装](https://cdn.jsdelivr.net/gh/zoe3971/my_images@main/dirsearch压缩包.png)  
**运行dirsearch**  
![dirsearch](https://cdn.jsdelivr.net/gh/zoe3971/my_images@main/dirsearch.png)  
***
## Writeup
### 第一题
[题目来源](https://www.nssctf.cn/problem/382)  
打开靶机，F12查看源代码，即可找到隐藏在网站源码中的FLAG  
![第一题](https://cdn.jsdelivr.net/gh/zoe3971/my_images@main/第一题.png)  
### 第二题
[题目来源](https://www.qsnctf.com/#/main/driving-range?page=1&category=&difficulty=&keyword=robots.txt)  
访问https://域名+端口/robots.txt 得到3个文件名  
![文件名](https://cdn.jsdelivr.net/gh/zoe3971/my_images@main/文件名.png).  
访问secret.php，得到账号密码  
![账号密码](https://cdn.jsdelivr.net/gh/zoe3971/my_images@main/账号密码.png)   
用得到的账户密码登入拿到flag  
![flag](https://cdn.jsdelivr.net/gh/zoe3971/my_images@main/flag.png)  
![已攻克](https://cdn.jsdelivr.net/gh/zoe3971/my_images@main/已攻克.png)
### 第三题
[题目来源](https://www.nssctf.cn/problem/3412)  
用Burp suite抓包
![地址](https://cdn.jsdelivr.net/gh/zoe3971/my_images@main/地址.png)  
访问node5.anna.nssctf.cn:21384地址，得到php  
![php](https://cdn.jsdelivr.net/gh/zoe3971/my_images@main/php.png)  
这段代码的意思是：php文件里面定义了flag变量，接收一个名为moe的GET参数，如果moe的值等于"flag"，就会输出$flag  
拿到flag  
![1](https://cdn.jsdelivr.net/gh/zoe3971/my_images@main/1.png)  
***
## Linux  
### 搭建过程
**安装VMware虚拟机**  
参考博客[vmware](https://blog.csdn.net/xuewzj888/article/details/157842709?spm=1001.2101.3001.6650.4&utm_medium=distribute.pc_relevant.none-task-blog-2~default~YuanLiJiHua~Position-4-157842709-blog-145380408.235%5Ev43%5Epc_blog_bottom_relevance_base2&depth_1-utm_source=distribute.pc_relevant.none-task-blog-2~default~YuanLiJiHua~Position-4-157842709-blog-145380408.235%5Ev43%5Epc_blog_bottom_relevance_base2&utm_relevant_index=7)  
![VMware](https://cdn.jsdelivr.net/gh/zoe3971/my_images@main/vmware.png)  
**在VMware上安装Ubuntu系统**  
参考博客[Ubuntu](https://cloud.tencent.com/developer/article/2417995)
![ubuntu](https://cdn.jsdelivr.net/gh/zoe3971/my_images@main/ubuntu.png)  
![hh](https://cdn.jsdelivr.net/gh/zoe3971/my_images@main/hh.png)  
### 学习笔记
  Linux 是一套免费使用和自由传播的类 Unix 操作系统，是一个基于 POSIX 和 UNIX 的多用户、多任务、支持多线程和多 CPU 的操作系统。  
  Linux 能运行主要的 UNIX 工具软件、应用程序和网络协议。它支持 32 位和 64 位硬件。Linux 继承了 Unix 以网络为核心的设计思想，是一个性能稳定的多用户网络操作系统。
#### 1.命令格式
>命令 [- 选项] [参数]  
查看帮助：命令 --help、man 命令
#### 2基础操作
>**目录查看与切换**  
>>ls：列出目录内容  
ls -a：显示隐藏文件  
ls -l：显示详细权限、大小等信息  
pwd：查看当前所在路径  
cd：切换目录  
cd ..：返回上一级  
cd ~：回到用户主目录

>**文件与目录管理**  
>>touch 文件名：新建空文件  
mkdir 目录名：创建目录  
mkdir -p 目录/子目录：递归创建多级目录  
rm 文件名：删除文件   
rm -r 目录：递归删除目录 
rm -f：强制删除，不提示 

>**文件复制、移动、查看**  
>>cp 源 目标：复制文件  
cp -r 源目录 目标目录：复制目录  
mv 源 目标：移动 / 重命名  
cat 文件名：查看全部内容  
more 文件名：分页查看文件 

>**查找与搜索**  
>>grep "关键词" 文件：在文件中搜索文本  
grep -n：显示行号  
find 路径 -name "文件名"：按文件名查找文件

#### 3常用操作  
>**链接**  
>>软链接：ln -s 源文件 链接名（类似快捷方式）

>**压缩与解压**  
>>压缩：tar -zcvf 压缩包名.tar.gz 要压缩的文件  
解压：tar -zxvf 压缩包名.tar.gz

>**权限管理**  
>>chmod 权限 文件名：修改文件 / 目录权限  
chown 用户名:组 文件：更改所有者与所属组  

>**进程管理**  
>>ps aux：查看系统所有进程  
top：动态实时监控进程  
kill 进程号：结束进程  
kill -9 进程号：强制结束进程  

>**远程与后台**  
>>ssh 用户名@IP：远程登录服务器  
scp 本地文件 用户名@IP:路径：远程拷贝文件  
后台运行：nohup 命令 &（关闭终端仍执行）  
#### 4技巧操作  
>Tab：命令、路径自动补全  
Ctrl+C：终止当前正在运行的程序  
\>：覆盖重定向（命令 > 文件）  
\>>：追加重定向（命令 >> 文件）  
|：管道符，将前一命令结果传给后一命令  
