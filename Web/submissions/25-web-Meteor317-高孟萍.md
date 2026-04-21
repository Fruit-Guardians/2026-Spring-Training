id:20253002787   Meteor317  
方向: web

## 一、软件/插件安装
### 1、hackbar插件
浏览器渗透测试插件，用于参数编码解码、数据包测试。  
<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/67478909/1776488388785-323b77e9-2923-4c5b-8fd4-83e6c50808bd.png)

### 2、dirsearch安装
网站目录扫描工具，用于探测网站后台隐藏路径。  
<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/65057214/1775964645561-5748c845-b502-4664-a194-0ad8251490b2.png)

### 3.Burpsuite
Web抓包代理工具，拦截修改HTTP数据包，Web漏洞测试核心工具。  
<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/67478909/1776490643360-f48fa47e-1267-4250-8d79-7dde992dae8f.png)



### 4.VMware虚拟机
安装虚拟机，搭建Linux本地靶场环境。  
<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/jpeg/67478909/1776585760312-99e45ca1-21fa-4bf0-ae50-dd8698ab4790.jpeg)  


## 二、Linux基础指令
### 文件目录操作
ls      # 列出当前目录所有文件与文件夹

cd      # 切换进入指定目录

pwd     # 查看当前所在目录绝对路径

mkdir   # 新建文件夹

cp      # 复制文件/文件夹

mv      # 移动、重命名文件/文件夹

rm      # 删除文件/文件夹

### 文件查看
cat     # 快速查看文件全部内容

more    # 分页查看文件

less    # 高级分页查看文件

head    # 查看文件开头内容

tail    # 查看文件结尾内容

### 系统权限网络
uname   # 查看系统版本信息

top     # 实时查看系统进程、资源占用

ps      # 查看进程信息

df      # 查看磁盘空间占用

free    # 查看内存占用情况

chmod   # 修改文件权限

chown   # 修改文件所属用户

ping    # 测试网络连通性

curl    # 命令行发起HTTP网络请求

### 压缩查找
tar     # 文件压缩、解压操作

find    # 全系统查找文件位置

grep    # 在文件中搜索指定内容

## 三、HTTP协议基础
1. 基础概述

 HTTP是Web客户端与服务器通信的应用层协议，基于TCP、请求-响应模型、无状态明文传输，主流版本HTTP/1.1。

 

2. 请求报文（4段：请求行→请求头→空行→请求体）

 请求行格式

  请求方法 URL HTTP/1.1 

常用方法：

 GET：参数在URL，无请求体，查询数据

POST：参数在请求体，提交表单/登录数据

 HEAD：仅返回响应头，用于绕过GET检测

 OPTIONS：探测服务器支持的请求方法

 高频请求头（键:值）

 Host：目标主机

 Referer：请求来源

 User-Agent：客户端浏览器信息

 Cookie：会话身份（修改 is_admin=1 可提权绕过）

 空行：分隔头和体；GET无请求体，POST有请求体。

 

 3. 响应报文（4段：状态行→响应头→空行→响应体）

 状态行格式

 HTTP/1.1 状态码 描述 

常用状态码：

200成功、302重定向、403无权、404不存在、500服务器错误

响应头：服务器信息；响应体：返回页面数据。

## 四、CTF题目练习
### 1.
**思路**

 题目名称gift_F12为明确提示，本题考点为网页前端源码泄露。flag隐藏在网页HTML源代码中，无需等待页面倒计时，通过查看网页源代码即可获取flag。

 **EXP**

 打开靶场地址 [http://node7.anna.nssctf.cn:28857](http://node7.anna.nssctf.cn:28857) ，使用快捷键 Ctrl+U 打开网页源代码，在源码中搜索flag关键字，提取得到flag：

 <font style="color:rgb(0, 0, 0);"> "WLLMCTF{We1c0me_t0_WLLMCTF_Th1s_1s_th3_G1ft}"</font>

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/67478909/1776587721939-c9272c7a-9d9d-4aa7-8945-3cdd5cdee2ba.png)  
<font style="color:rgb(0, 0, 0);">flag = "WLLMCTF{We1c0me_t0_WLLMCTF_Th1s_1s_th3_G1ft}"</font>

### 2.
<font style="color:rgba(0, 0, 0, 0.88);background-color:rgba(255, 255, 255, 0.6);">访问secret.php</font>

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/67478909/1776590257292-2f05666d-7795-4bb6-9f14-6b4c7dad7ff8.png)

<font style="color:rgba(0, 0, 0, 0.88);background-color:rgba(255, 255, 255, 0.6);">得到账号密码</font>

<font style="color:rgba(0, 0, 0, 0.88);background-color:rgba(255, 255, 255, 0.6);">用得到的账户密码登入拿到flag</font>

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/67478909/1776590444713-5d97b5bb-5d9f-4a32-89cb-2f768b21aa0f.png)

flag{7e0c55e1019d4f56a4c23108f519b804}

### 3.
GET   提交较简单的数据

POST 提交较为复杂的数据





