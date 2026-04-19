# 应用程序的搭建

## Hackbar

在GitHub仓库里获取安装包,网址[github源码仓库](https://github.com/Mr-xn/hackbar2.1.3)下载安装包并解压到一个固定的文件夹。

在谷歌浏览器输入<chrome://extensions/>，再选择"加载已解压的扩展程序"。  

![](https://qczn-1422253280.cos.ap-guangzhou.myqcloud.com/ScreenShot_2026-04-14_100635_048.png)


## Burp Suite  

下载JDK并配置有关Python的环境变量，再下载Burp Suite 社区版。参照网址[腾讯云服务器配置教程](https://cloud.tencent.com/developer/article/1880388)

![](https://qczn-1422253280.cos.ap-guangzhou.myqcloud.com/ScreenShot_2026-04-14_105103_763.png)


## dirsearch

打开 Dirsearch 的 GitHub 主页，网址[dirsearch仓库](https://github.com/maurosoria/dirsearch)，下载压缩包，解压到指定文件夹。  

在文件夹窗口地址栏输入cmd，进入命令行，输入文件夹的路径（`cd C:\Users\15327\Downloads\dirsearch-master`），再安装环境依赖（依次输入`pip install -r requirements.txt`,`python dirsearch.py -h`）

![](https://qczn-1422253280.cos.ap-guangzhou.myqcloud.com/ScreenShot_2026-04-14_104921_569.png)

![](https://qczn-1422253280.cos.ap-guangzhou.myqcloud.com/ScreenShot_2026-04-13_192448_745.png)


## write up

## 第一题

按F12打开开发者工具，发现源码折叠了，不全部显示，选中html，选择复制 other html，创建记事本，复制内容粘贴到记事本上，即为网页源码（或者直接按Ctrl+U组合键）  

![](https://qczn-1422253280.cos.ap-guangzhou.myqcloud.com/ScreenShot_2026-04-14_164140_545.png)


## 第二题

初始加载环境的界面有一个robots.txt，在url访问行加上/ `robots.txt`,发现登进去一个界面，发现写着不允许访问，列了三个路径，尝试着把路径分别加到url网址栏后面，发现加上/`secret.php`时出现一个界面，给了username和password，用这两个填入初始环境的，登录的界面，登陆成功。

![](https://qczn-1422253280.cos.ap-guangzhou.myqcloud.com/ScreenShot_2026-04-14_164936_364.png)

![](https://qczn-1422253280.cos.ap-guangzhou.myqcloud.com/ScreenShot_2026-04-14_165345_830.png)

## 第三题

初始环境里的php代码分析  

`$moe = $_GET['moe'];`是获取moe的值，`if ($moe == "flag")`是判断是否为flag，`echo $flag`如果相等就输出flag的值。需要构造一个 HTTP GET 请求，带上参数 `moe`，判断它的值是否为 `flag`  

直接在浏览器的url网址上修改，加上`?moe=flag`后再访问，或者用Python的`request`库进行GET请求（在命令行窗口执行）代码`import requests`,`url="题目环境里的网址加上判断?moe=flag"`,`response=requests.get(url)`,`print(response.text)`。

![](https://qczn-1422253280.cos.ap-guangzhou.myqcloud.com/ScreenShot_2026-04-14_175751_947.png)

# 虚拟机的搭建和基础命令笔记

## vmware Workslation

参照网址[2026 最新vmware17虚拟机安装教程（保姆级，图文讲解，带安装包）-CSDN博客](https://blog.csdn.net/xuewzj888/article/details/157842709?spm=1001.2101.3001.6650.4&utm_medium=distribute.pc_relevant.none-task-blog-2~default~YuanLiJiHua~Position-4-157842709-blog-145380408.235^v43^pc_blog_bottom_relevance_base2&depth_1-utm_source=distribute.pc_relevant.none-task-blog-2~default~YuanLiJiHua~Position-4-157842709-blog-145380408.235^v43^pc_blog_bottom_relevance_base2&utm_relevant_index=7)

（激活秘钥也是在百度上找的）如图是打开vmware的主页面
![](https://qczn-1422253280.cos.ap-guangzhou.myqcloud.com/ScreenShot_2026-04-14_181353_263.png)

## Ubuntu

参照网址[虚拟机VMware上安装Ubuntu系统（详细图文教程）-腾讯云开发者社区-腾讯云](https://cloud.tencent.com/developer/article/2417995)

如图是打开Ubuntu的主页面  

![](https://qczn-1422253280.cos.ap-guangzhou.myqcloud.com/ScreenShot_2026-04-14_181939_635.png)

## 虚拟机的基础命令

is->查看当前文件夹的内容 pwd->查看当前文件夹 touch[文件名]->如果文件不存在，新建文件  

mkdir[目录名]->创建目录 rm[文件名]->删除指定文件 clear->清屏 `ctrl + shift + =` 放大终端窗口的字体显示  `ctrl + -` 缩小终端窗口的字体显示  tab->系统自动补全文件/目录/命令

find [路径] -name “*.py”->查找指定路径下扩展名是 .py 的文件，包括子目录  

man 是 manual 的缩写，是 Linux 提供的一个 手册，包含了绝大部分的命令、函数的详细使用

空格->手册页下一行 b->回滚一屏  f->前滚一屏  q->退出  

tar -cvf 打包文件.tar 被打包的文件／路径.->打包文件  tar -xvf 打包文件.tar-> 解包文件

tar -zcvf 打包文件.tar.gz 被压缩的文件／路径->压缩文件 tar -zxvf 打包文件.tar.gz->解压缩文件  

sudo apt install 软件包->安装软件  sudo apt remove 软件名->卸载软件  

cd->切换到当前用户的主目录(/home/用户目录),cd .->保持在当前目录不变,cd …->切换到上级目录  

# http协议

http是超文本运输协议，在浏览器和服务器之间进行数据的传输，浏览器和服务器必须遵守相同的规则建立TCP链接，客户端把请求数据发给服务器，服务器直接根据数据响应的界面呈现给客户端。

https是超文本传输安全协议，与http不同，https的传输过程是加密的，TCP建立后不直接发数据，先进行TLS/SSL握手，建立加密通道，用会话秘钥加密成乱码发送，服务器使用相同的会话秘钥解密得到原文，在进行响应，重新加密后发挥客户端。

# PHP

php是超文本预处理器，是一种开源服务器的脚本语言，用户在浏览器输入网址，Web服务器接收后发给PHP引擎，PHP解析并执行代码，生成HTML内容，返回给Web服务器，浏览器再解析HTML再把生成的界面返回给用户。用户只能看到HTML，看不到PHP的源码。PHP工作时独立执行每次请求，结束后释放内存，是动态的。PHP可以嵌入在HTML中，但是先执行PHP，再输出HTML。

# 
