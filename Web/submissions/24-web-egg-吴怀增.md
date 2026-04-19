# write up

## 1.SWPUCTF 2021 新生赛

题目来源[SWPUCTF 2021 新生赛]([[SWPUCTF 2021 新生赛]gift_F12 - NSSCTF](https://www.nssctf.cn/problem/382))

这一题题目有提示，gift_f12意味着用f12开发者工具打开，查找元素即可找到flag。这里可以用Ctrl+f提高检索效率

一般来说都是在脚本script这里

![](C:\Users\ASUS\AppData\Roaming\marktext\images\2026-04-18-18-06-50-image.png)

<img src="file:///C:/Users/ASUS/AppData/Roaming/marktext/images/2026-04-18-18-07-52-image.png" title="" alt="" width="608">

## 2.Web安全入门指北—GET

题目来源[[MoeCTF 2021]Web安全入门指北—GET]([[MoeCTF 2021]Web安全入门指北—GET - NSSCTF](https://www.nssctf.cn/problem/3412))

![](C:\Users\ASUS\AppData\Roaming\marktext\images\2026-04-18-20-51-41-image.png)

这一题是php语言用get请求，一般来说可以用hackbar插件进行get请求，把moe="flag"就可以获得flag

我这里用python编写了一个小脚本获取flag

![](C:\Users\ASUS\AppData\Roaming\marktext\images\2026-04-18-20-55-19-image.png)

其中url为题目的端口号

这样依旧可以拿到flag

![](C:\Users\ASUS\AppData\Roaming\marktext\images\2026-04-18-21-10-39-image.png)

## 3. [qsnctf-NO.0902robots.txt]([青少年CTF练习平台](https://www.qsnctf.com/#/main/driving-range?page=1&category=&difficulty=&keyword=robots.txt&user_answer=&user_favorite=&tag_ids=&challenge_id=902))

根据提示访问robot.txt

![](C:\Users\ASUS\AppData\Roaming\marktext\images\2026-04-18-21-53-15-image.png)

这里有admin,login,secret三个，一般来说secret大概率是，进去后如下

![](C:\Users\ASUS\AppData\Roaming\marktext\images\2026-04-18-21-55-52-image.png)

从而拿到了用户账号密码

获取flag![](C:\Users\ASUS\AppData\Roaming\marktext\images\2026-04-18-21-56-58-image.png)

# 工具

## 1.bursuip

可以阅读这个博客([BurpSuite下载和安装保姆级教程（附官网安装包，非常详细）_burpsuite官网下载-CSDN博客](https://blog.csdn.net/ebiancheng/article/details/156227852))

下载好burpsuite文件

![](C:\Users\ASUS\AppData\Roaming\marktext\images\2026-04-18-23-39-45-image.png)

运行bp一键运行（要注意的是你的电脑要配置Java环境，用国内的镜像下载的快一些）

![](C:\Users\ASUS\AppData\Roaming\marktext\images\2026-04-18-23-41-17-image.png)

点击*run*,之后把license复制到key中

![](C:\Users\ASUS\AppData\Roaming\marktext\images\2026-04-18-23-42-58-image.png)

![](C:\Users\ASUS\AppData\Roaming\marktext\images\2026-04-18-23-44-47-image.png)![](C:\Users\ASUS\AppData\Roaming\marktext\images\2026-04-18-23-45-01-image.png)

![](C:\Users\ASUS\AppData\Roaming\marktext\images\2026-04-18-23-46-00-image.png)

## 2. dirsearch

建议阅读([dirsearch使用教程_dirsearch的使用方法-CSDN博客](https://blog.csdn.net/m0_48574718/article/details/129244162))

可以从里面下载dirsearch安装包

再输入*pip3 install -r requirements.txt*安装依赖

这里查看大概用法![](C:\Users\ASUS\AppData\Roaming\marktext\images\2026-04-19-00-57-32-image.png)

一般常用的命令

python dirsearch.py -u http://xxxx        //日常使用

python dirsearch.py -u http://xxxx -r        //递归扫描，不过容易被检测

python dirsearch.py -u http://xxxx -r -t 30        //线程控制请求速率

python dirsearch.py -u http://xxxx -r -t 30 --proxy 127.0.0.1:8080        //使用代理 

## 3.hackbar

在Google浏览器的插件商城搜索，获取

# linux

## 虚拟机

这里的虚拟机是我培训之前就已经安装过了的，所以没有安装截图

![](C:\Users\ASUS\AppData\Roaming\marktext\images\2026-04-19-01-18-57-image.png)

打开之前配置的kali虚拟镜像（这里的镜像下载建议使用国内镜像，下载速度飞快）

启动

![](C:\Users\ASUS\AppData\Roaming\marktext\images\2026-04-19-01-20-07-image.png)

![](C:\Users\ASUS\AppData\Roaming\marktext\images\2026-04-19-01-25-39-image.png)

开机后输入账号密码进入

![](C:\Users\ASUS\AppData\Roaming\marktext\images\2026-04-19-01-26-28-image.png)

之前我配置的时候他还需要配置网卡，内存，运行核等，这个可以看哔站上的视频跟着学。

## 常用命令

1.目录与文件基础操作

ls                             列出当前目录所有文件
ls -l                         详细查看文件权限、大小、修改时间
cd 文件夹路径       切换进入指定目录
cd ..                         返回上一级目录
cd /                         回到系统根目录
pwd                        查看当前所在完整路径
mkdir 文件夹名     新建空白文件夹
touch 文件名.txt   新建空白文件
cat 文件名              查看文件内部全部内容
cp 源文件 目标路径  复制文件/文件夹
mv 旧名 新名             重命名文件/文件夹
mv 文件 目标路径      移动文件到其他位置
rm 文件名                   删除普通文件
rm -rf 文件夹名          强制删除文件夹（删除后无法恢复）

2.磁盘硬盘管理命令

df -h                     查看全部分区已用/剩余硬盘空间（人性化大小单位）
du -sh 文件夹     查看单个文件夹占用的硬盘容量
mount                挂载外接/磁盘分区
umount               卸载已挂载的分区

3.系统进程权限管理

ps aux             查看系统所有后台运行程序
top                   实时监控CPU、内存占用状态
kill 进程ID        强制关闭卡死的异常进程
sudo 命令         给后续命令获取管理员root最高权限

4.软件安装管理

sudo apt update              更新软件仓库源列表
sudo apt install 软件名   在线安装指定软件
sudo apt remove 软件名  卸载已安装软件
sudo apt autoremove     清理系统无用残留依赖

（这里apt 和 install经常会使用）

5.系统关机重启

reboot       重启操作系统
poweroff  正常关闭电脑

还有一个重点命令grep,语法为grep [可选参数] 搜索关键词 目标文件/路径

作用：在文件内容、命令输出里**精准查找匹配指定字符串**

<style>
 table { border-collapse: collapse; width: 100%; }
 th, td { border: 1px solid #ccc; padding: 8px; text-align: left; }
 </style>

<style>
 table { border-collapse: collapse; width: 100%; }
 th, td { border: 1px solid #ccc; padding: 8px; text-align: left; }
 </style>

| 参数   | 作用                   |
| ---- | -------------------- |
| `-n` | 显示匹配内容所在**行号**       |
| `-i` | 忽略大小写，大小写不敏感匹配       |
| `-r` | 递归搜索：遍历文件夹内**所有文件**  |
| `-v` | 反向匹配：显示**不包含**关键词的行  |
| `-l` | 只输出匹配到的**文件名**，不展示内容 |
| `-w` | 全单词精准匹配，不匹配单词片段      |
| `-E` | 支持多关键词、正则表达式匹配       |

还有一个管道符|搭配使用效果会很好

命令A | 命令B

把**前一条命令的屏幕输出**，当做**后一条命令的输入内容**

举个和grep搭配的例子：

*ps aux | grep burp*（查找Burp套件是否正在后台运行 ）

## php

1.基础语法结构

```php
<?php
echo "PHP代码正常显示";
$a = 123;
?>
```

可嵌套在 HTML 中使用且严格区分**大小写**（变量、函数名）

2.输入语法

```
<?php
// 1. echo：输出字符串/变量（推荐，效率最高）
echo "你好";
echo 123;

// 2. 拼接字符串用 . 符号
echo "姓名：" . "张三";
?>
```

3.变量和常量

```
<?php
// 变量以 $ 开头，字母/下划线开头
$name = "小明";
$age = 18;
$is_student = true;
$height = 1.75;

// 输出变量
echo $name;
?>
```

<?php
// 变量以 $ 开头，字母/下划线开头
$name = "小明";
$age = 18;
$is_student = true;
$height = 1.75;
// 输出变量
echo $name;
?>

```
<?php
// 变量以 $ 开头，字母/下划线开头
$name = "小明";
$age = 18;
$is_student = true;
$height = 1.75;

// 输出变量
echo $name;
?>
```

4.条件判断

if else

```
<?php
$age = 20;
if ($age >= 18) {
    echo "成年";
} else {
    echo "未成年";
}
?>
```

5.foreach循环（数组用）

```
<?php
$arr = [1,2,3];
foreach ($arr as $value) {
    echo $value;
}
?>
```

6.数组

索引

```
<?php
$fruit = ["苹果", "香蕉", "橙子"];
echo $fruit[0]; // 输出：苹果
?>
```

键值对

```
<?php
$user = [
    "name" => "张三",
    "age" => 20,
    "city" => "北京"
];
echo $user["name"]; // 输出：张三
?>
```

7.超全局变量（我认为是重点）

```
<?php
// 1. $_GET：接收地址栏/GET表单数据
$id = $_GET["id"];

// 2. $_POST：接收POST表单数据（登录/注册专用）
$username = $_POST["username"];

// 3. $_SERVER：获取服务器信息
echo $_SERVER["REMOTE_ADDR"]; // 客户端IP
?>
```

可以进行表单交互
