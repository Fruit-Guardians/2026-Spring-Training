> ID：Tak3
>
> 方向：Web
>
> 日期：2026-04-15
>

# WriteUp
## [SWPUCTF 2021 新生赛]gift_F12
> 来源：[[SWPUCTF 2021 新生赛]gift_F12](https://www.nssctf.cn/problem/382)
>
> 靶机/远程地址：[http://node7.anna.nssctf.cn:22506/](http://node7.anna.nssctf.cn:29671/)
>
> 工具：浏览器开发者工具（F12）、Chrome 146.0.7680.178
>

访问靶机，页面显示：
![](https://cdn.nlark.com/yuque/0/2026/png/65087184/1775916360671-15d8dce9-c836-4587-85d3-a1fdc6e6f1aa.png)

根据题目描述，使用`F12`查看源代码，`ctrl＋F`尝试搜索关键词`flag`，发现：
![](https://cdn.nlark.com/yuque/0/2026/png/65087184/1775916578964-745f8382-3448-423b-8209-749d0f385db6.png)

从而得到 flag：`NSSCTF{We1c0me_t0_WLLMCTF_Th1s_1s_th3_G1ft}`

## [MoeCTF 2021]Web安全入门指北—GET
> 来源：[[MoeCTF 2021]Web安全入门指北—GET](https://www.nssctf.cn/problem/3412)
>
> 靶机/远程地址：[http://node5.anna.nssctf.cn:21610/](http://node7.anna.nssctf.cn:29671/)
>
> 工具：HackBar 1.2.8、Chrome 146.0.7680.178
>

访问靶机，页面显示：
![](https://cdn.nlark.com/yuque/0/2026/png/65087184/1775916788177-e18f1237-cf2d-4991-9ee2-7b4346e951c2.png)

```php
<?php
include "flag.php";
$moe = $_GET['moe'];
if ($moe == "flag") {
    echo $flag;
}else {
    highlight_file(__FILE__);
}
```

根据 php 代码内容，需要使用`GET`方式传递参数`moe`，当`moe=flag`时方可得到本题 flag，使用 HackBar 插件，构造 payload：

```php
?moe=flag
```

页面响应：
![](https://cdn.nlark.com/yuque/0/2026/png/65087184/1775917083291-73448054-02a4-4bbc-be63-5588b7981c47.png)

从而得到 flag：`NSSCTF{d676d5a3-0fb6-4bf3-8e0b-3db714153571}`

## [qsnctf-NO.0902]robots.txt
> 来源：[[qsnctf-NO.0902]robots.txt](https://www.qsnctf.com/#/main/driving-range?page=1&category=&difficulty=&keyword=robots.txt&user_answer=&user_favorite=&tag_ids=&challenge_id=902)
>
> 靶机/远程地址：[http://challenge.qsnctf.com:51310/](http://challenge.qsnctf.com:51310/)
>
> 工具：Chrome 146.0.7680.178
>

访问靶机，页面显示：
![](https://cdn.nlark.com/yuque/0/2026/png/65087184/1776060099741-c27b15a1-609b-4b5c-a4d3-d8125d24f716.png)

根据提示，访问当前靶机地址下的文件`robots.txt`,访问`靶机地址/robots.txt`页面响应：
![](https://cdn.nlark.com/yuque/0/2026/png/65087184/1776060116929-05239f0c-8714-41c6-a4fd-6a90f3e53ad9.png)

显然，`secret.php`才是下一步要查看的目标文件，访问`靶机地址/secret.php`，页面响应：
![](https://cdn.nlark.com/yuque/0/2026/png/65087184/1776060135299-d19593c1-9925-4d00-bc20-46be6ea5d5cd.png)

从而得到登陆所需的用户名和密码，拿去登录：
![](https://cdn.nlark.com/yuque/0/2026/png/65087184/1776060229045-0276154a-3004-4996-bb37-ed0fbf9e1b8b.png)
![](https://cdn.nlark.com/yuque/0/2026/png/65087184/1776060242929-c50407f2-eb0d-4092-87e2-47f72e2ca449.png)

从而得到 flag：`flag{4be845f3ffb04ffc880e395c579b6906}`

# 工具安装
## HackBar
打开 Chrome，访问[Chrome 应用商店](https://chromewebstore.google.com/category/extensions?utm_source=ext_sidebar&hl=zh-CN)：
![](https://cdn.nlark.com/yuque/0/2026/png/65087184/1776079605052-ac96a80f-3e88-4d59-8e40-74940310f02a.png)

在搜索栏处搜索`HackBar`，或直接访问[详情页面](https://chromewebstore.google.com/detail/hackbar/ginpbkfigcoaokgflihfhhmglmbchinc?hl=zh-CN&utm_source=ext_sidebar)：
![](https://cdn.nlark.com/yuque/0/2026/png/65087184/1776079793490-808a40fd-95ce-47f7-a558-e978b19288af.png)

单击获取`获取`，从而完成安装。访问网页时，`右键`→`检查`→`HackBar`即可使用该插件。
![](https://cdn.nlark.com/yuque/0/2026/png/65087184/1776080030250-b40101c6-00d2-4604-bffb-e179bbe82a0a.png)

## Burp Suite ＋ Proxy SwitchyOmega 3 (ZeroOmega)
访问[下载页面](https://portswigger.net/burp/releases/professional-community-2026-3-2?requestededition=community&requestedplatform=)：
![](https://cdn.nlark.com/yuque/0/2026/png/65087184/1776080336179-c990de7d-e1e0-41ed-a40b-d2740463f72f.png)

保持默认选择[Burp Suite Community Edition，Windows (x64)]不变，单击`DOWNLOAD`完成下载。双击程序进行安装：
![](https://cdn.nlark.com/yuque/0/2026/png/65087184/1776080729969-04a77a94-5c2d-49dd-845b-beb8d6661e60.png)

由于电脑之前已经安装了，为做演示，选择`No，instal into a different directory`，`Next`：
![](https://cdn.nlark.com/yuque/0/2026/png/65087184/1776080897349-55bfa896-9b69-49d1-b7e8-7065b30a495b.png)

选择安装地址，`Next`：

![](https://cdn.nlark.com/yuque/0/2026/png/65087184/1776080956691-91a1cb90-3584-4c0b-927c-3fc18626ac90.png)

`Next`后等待安装，`Finish`以完成安装。双击启动程序：
![](https://cdn.nlark.com/yuque/0/2026/png/65087184/1776082907860-6b3c2640-47a9-4fee-8fff-a14e14c83daf.png)

`Next`：
![](https://cdn.nlark.com/yuque/0/2026/png/65087184/1776082944284-0984c218-f7d8-44d3-81fb-9ae30b4a4189.png)

`Start Burp`后，打开`Settings`：
![](https://cdn.nlark.com/yuque/0/2026/png/65087184/1776083341031-6783afd4-7608-4ca4-9668-6924e234e154.png)

确认当前监听地址为`127.0.0.1:8080`，在启动 Burp Suite 的状态下访问`http://127.0.0.1:8080/`，页面响应：
![](https://cdn.nlark.com/yuque/0/2026/png/65087184/1776095627198-fadf47fa-041a-456a-93dc-9cb79bc102e0.png)

单击`CA Certificate`下载并双击证书`cacert.der`：
![](https://cdn.nlark.com/yuque/0/2026/png/65087184/1776097318515-2ee2bfa4-84d3-4d4d-8eb6-09a8c6bb59f0.png)

`安装证书...`→`本地计算机`→`下一步`→`将所有的证书都放入下列存储`→`浏览...`→`受信任的根证书颁发机构`→`确定`→`下一步`→`完成`，具体如下：
![](https://cdn.nlark.com/yuque/0/2026/png/65087184/1776097581797-f224c16c-8f87-4adf-8bc3-2d6d52b55ac3.png)
![](https://cdn.nlark.com/yuque/0/2026/png/65087184/1776097596633-6e46a48c-13ba-403e-872c-97c8f14bff93.png)
![](https://cdn.nlark.com/yuque/0/2026/png/65087184/1776097604723-1b775f99-6d3e-458f-aaa8-11212268a22b.png)
![](https://cdn.nlark.com/yuque/0/2026/png/65087184/1776097613280-fed81840-12b6-42d0-9307-c7e4ae85fb5c.png)

成功导入证书后，在 Chrome 证书管理器（chrome://certificate-manager/localcerts）开启`使用从操作系统导入的本地证书`。在 Chrome 上安装插件`Proxy SwitchyOmega 3 (ZeroOmega)`，[此处为下载链接](https://chromewebstore.google.com/detail/proxy-switchyomega-3-zero/pfnededegaaopdmhkdmcofjmoldfiped?hl=zh-CN&utm_source=ext_sidebar)，安装方式同 HackBar。安装并启用该插件，在其设置界面（chrome-extension://pfnededegaaopdmhkdmcofjmoldfiped/options.html#!/theme）：
![](https://cdn.nlark.com/yuque/0/2026/png/65087184/1776084767720-20f65bfc-e0da-4812-ad38-54bca0d24166.png)

`新建情景模式...`→ 自定义情景模式名称 →`代理服务器`→ `创建`：
![](https://cdn.nlark.com/yuque/0/2026/png/65087184/1776085009112-572ad7eb-9ede-4465-a5d0-d4b6fbe5a324.png)

创建完成后，在刚才创建的情景模式下，清空不代理的地址列表，修改代理协议为`HTTP`，将代理服务器与代理端口作如下修改：
![](https://cdn.nlark.com/yuque/0/2026/png/65087184/1776093005044-e170b8c7-9ea9-4afa-962e-55872f5b2859.png)

`应用选项`，至此完成抓包前的准备操作。

## dirsearch
[参考链接](https://zhuanlan.zhihu.com/p/1999235997301490688)
![](https://cdn.nlark.com/yuque/0/2026/png/65087184/1776249887389-c8ce8991-c3d5-4b47-9885-2120e3de0b38.png)

# 搭建Linux环境（Ubuntu 24.04.3 LTS）
1. 下载并运行`VMware Workstation Pro安装向导`，按照提示完成`VMware Workstation Pro`的安装：
![](https://cdn.nlark.com/yuque/0/2026/png/65087184/1769621953117-e96c3d37-6ab4-46ab-adc9-3cbdeebc0e95.png)
2. 访问[<font style="color:rgb(65, 131, 196);">https://cn.ubuntu.com/download/desktop</font>](https://cn.ubuntu.com/download/desktop)下载`Ubuntu24.04.3-desktop-amd64`光盘映像文件。
3. 打开VMware Workstation Pro，`新建虚拟机`，`运行新建虚拟机向导`，选择`自定义（高级）`选项，按提示依次选择`虚拟机硬件兼容性`、`稍后安装操作系统`、并按提示完成虚拟机配置设置：
![](https://cdn.nlark.com/yuque/0/2026/png/65087184/1769624110011-3d0fa681-a6dc-4fdc-a2df-90868c314ed8.png)
![](https://cdn.nlark.com/yuque/0/2026/png/65087184/1769624549883-f0ba8655-831e-497d-b112-7a8997463240.png)
![](https://cdn.nlark.com/yuque/0/2026/png/65087184/1769624566669-426bbc80-e09e-4ee5-867b-c3ec432cc4ba.png)
![](https://cdn.nlark.com/yuque/0/2026/png/65087184/1769624590214-252d123a-17b2-4647-b504-c279fc2cb8b6.png)
4. 启动虚拟机，根据提示进行设置，最终完成Ubuntu系统安装与搭建：
![](https://cdn.nlark.com/yuque/0/2026/png/65087184/1769662380191-023ed5e7-8b7e-4084-b1a0-87a0f710ff05.png)

  


# Linux 基础指令
```markdown
1. ls：列出⽬录内容
● ls：列出当前⽬录的⽂件和⽂件夹。
● ls -l：以详细列表形式显示。
● ls -a：显示所有⽂件，包括隐藏⽂件。
● ls /：列出根⽬录内容。

2. cd：切换⽬录
● cd ⽬录名：进⼊指定⽬录。
● cd ..：返回上⼀级⽬录。
● cd ~：回到⽤户的主⽬录。

3. pwd：显示当前所在⽬录

4. mkdir：创建⽬录
● mkdir ⽬录名：创建⼀个新的⽬录。

5. touch：创建空⽂件
● touch file.txt：创建⼀个名为 file.txt 的空⽂件。

6. cat：查看⽂件内容
● cat file.txt：输出⽂件内容。
● cat flag.txt：常⽤于查看 flag 内容。

7. echo：输出字符串或写⼊⽂件
● echo hello：输出 hello。
● echo hello > a.txt：写⼊到⽂件（覆盖）。
● echo hello >> a.txt：追加到⽂件末尾。

8. cp：复制⽂件或⽬录
● cp a.txt b.txt：复制⽂件。
● cp -r dir1 dir2：递归复制⽬录。

9. mv：移动或重命名
● mv a.txt b.txt：重命名或移动⽂件。

10. rm：删除⽂件或⽬录
● rm a.txt：删除⽂件。
● rm -r dir：删除⽬录及其内容。

11. chmod：修改权限
● chmod +x script.sh：给⽂件添加可执⾏权限。

12. ifconfig / ip a：查看⽹络信息
● ifconfig：旧命令，显示 IP 信息。
● ip a：现代命令，等效于 ifconfig。

13. wget / curl：下载⽂件
● wget http://example.com/file
● curl http://example.com/file -o file

14. uname：查看系统信息
● uname -a：显示内核和架构等信息。

15. whoami：查看当前⽤户 名

16. find：查找⽂件
● find / -name flag.txt：全盘搜索 flag ⽂件。
● find / -user root -perm -4000 -print> result.txt 提权。 

17. grep：搜索字符串
● grep root /etc/passwd：在系统的⽤户信息⽂件中查找名为 root 的账户信息。

18. tar：压缩/解压⽂件
```



# PHP 基础语法
## PHP 基础格式
+ PHP 脚本可以放在文本的任意位置
+ PHP 脚本以`<?php`开始，以`?>`结束
+ PHP 文件的默认扩展名是`.php`

```php
<?php
//执行的相关PHP代码
?>
```

## 变量声明
+ 弱类型+动态类型
+ 无需声明类型，会根据上下文自动转换类型
+ 所有变量必须以`$`开头
+ 变量名必须以字母或下划线字符开始，只能包含字母、数字及下划线
+ 变量名区分大小写

```php
$a = 10;
$a = "hello";
$y = 3.14;
```

## 内存管理
+ 自动内存管理（垃圾回收）
+ PHP 程序员不直接接触内存地址，极大地降低了开发难度，但也隐藏了安全风险（如反序列化漏洞）。

```php
$a = [1,2,3];
// 用完自动释放
```

## 表单数据
+ `$_GET`—— 接受 GET 请求传递的参数。

示例：`example.com/index.php?book=HELLOCTF`，你可以使⽤`$_GET['book']`来获取相应的值。

+ `$_POST`—— 接受 POST 请求传递的参数。

示例：对`example.com/index.php`进行 POST 传参，参数名为`book`内容为`HelloCTF`你可以使⽤`$_POST['book']`来获取相应的值。

+ `$_REQUEST`—— 接受 GET 和 POST 以及 Cookie 请求传递的参数。

示例：

```plain
- 如果你通过 URL 传递了⼀个参数 example.com/index.php?key=value_from_get，你可以通过 $_REQUEST['key'] 获取这个值。
- 如果你通过 POST 方法提交了⼀个表单，其中有⼀个名为 key 的字段且其值为 value_from_post ，你也可以通过 $_REQUEST['key'] 获取这个值。
- 如果你设置了⼀个名为 key 的 cookie，其值为 value_from_ value_from_cookie ，你可以使用 $_REQUEST['key'] 来获取这个值。
```

## 单引号与双引号
+ 单引号：不会解析变量。字符串里的内容会原样输出。
+ 双引号：会解析其中的变量，并输出变量的值。

```php
<?php
$string = "beautiful";
$time = "winter";

$str = 'This is a $string $time morning!';
$str2 = "This is a $string $time morning!";
echo $str. PHP_EOL;
echo $str2;
```

```plain
This is a $string $time morning!
This is a beautiful winter morning!
```

# HTTP 协议
## HTTP 协议相关概念
### HTTP 协议
HTTP (HyperText Transfer Protocol)，即超文本传输协议，是互联网上应用最为广泛的⼀种网络协议。它定义了浏览器（客户端）与服务器之间如何交换数据。HTTP 工作在 TCP/IP 模型之上，通常使用端口 80。

### 超文本
包含超链接的文本称为超文本

<a href="https://www.hnusec.com">HnuSec</a>

按 TCP/IP 四层模型进行分类：

| **层级** | **核心协议**              | 核心功能            |
| :------- | :------------------------ | :------------------ |
| 应用层   | HTTP，DNS，FTP，SMTP，SSH | 提供用户服务        |
| 传输层   | TCP，UDP                  | 端到端可靠/快速传输 |
| 网络层   | IP，ICMP，ARP             | 跨网络寻址与路由    |
| 链路层   | Ethernet，Wi-Fi，PPP      | 本地网络帧传输      |


## HTTP 的工作机制
### HTTP 请求和响应
HTTP 的基本工作原理是客户端（通常是 web 浏览器）向服务器发送请求，服务器接收到请求后，返回相应的资源。这些资源可以是网页、图像、音频文件、视频等。

+ 建立连接
+ 客户端发送 HTTP 请求
+ 服务器处理并返回 HTTP 相应
+ 关闭连接（或保持连接以备后用）

HTTP 协议自身不具备保存之前发送过的请或响应的功能。

### URL及其编码
URL 的全称是 Uniform Resource Locator，中文译为统⼀资源定位符。

URL 是 HTTP 请求的目标：HTTP 协议必须依靠 URL 才能知道要连接哪台服务器（域名/IP）以及请求该服务器上的哪个资源（路径）。

⼀个典型的 URL 由以下几个部分组成，每个部分都有其特定的功能：

https://www.example.com/path/to/file.php?id=1#section1

| **组成部分** | **说明**                                                 | **示例（基于示例 URL ）** |
| :----------- | :------------------------------------------------------- | :------------------------ |
| 协议         | 规定浏览器与服务器通信的“语言”和方式。                           |`https://`|
| 主机名/域名  | 指向互联网上存放资源的某台具体服务器的地址。             | `www.example.com`         |
| 端口         | 服务的“入口”。HTTPS 默认为443，HTTP 默认为 80。          | `:443`                    |
| 路径         | 资源在服务器上的存储位置，类似于电脑的目录。             | `/path/to/file.php`       |
| 查询参数     | 传递给服务器的额外数据，以`?`开始，`&`分隔键值对。       | `?id=1`                   |
| 锚点         | 指向页面内的特定位置（如某个标题），数据不发送给服务器。 | `#section1`               |

1. HTTP 请求的结构

- 请求行：请求方法、URL、版本协议
- 请求头：：客户端环境、身份验证
- 空行：区分头部和主体
- 请求体：发送给服务器的数据（仅在 POST/PUT 等方法中使用）

```plain
GET /index.html HTTP/1.1
Host: www.example.com
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:91.0) Gecko/201001
01 Firefox/91.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,*/
*;q=0.8
Accept-Encoding: gzip, deflate
Connection: keep-alive
```

1. 常见的 HTTP 请求方法

| **方法** | **作用**     | **安全角度说明**       |
| -------- | ------------ | ---------------------- |
| GET      | 获取资源     | 常用于查询、搜索、分页 |
| POST     | 提交数据     | 常用于登录、表单       |
| PUT      | 更新资源     | REST 风格 API          |
| DELETE   | 删除资源     | 高危操作               |
| HEAD     | 获取响应头   | 信息收集               |
| OPTIONS  | 查询支持方法 | 常用于 CORS            |

GET 方法：

数据附加在 URL 之后，以问号`?`开始，参数之间⽤`&`分隔。

```plain
GET /search.php?keyword=php&page=1 HTTP/1.1
Host: example.com
```

POST 方法：

数据放在请求体中，不会显示在 URL ⾥。

```plain
POST /login.php HTTP/1.1
Host: example.com
Content-Type: application/x-www-form-urlencoded
Content-Length: 27
username=admin&password=123456
```

1. 常见的 HTTP 请求头

基础信息类：

- `Host`: 指定请求的服务器域名和端口号。
- `User-Agent`: 告诉服务器客户端的浏览器类型、操作系统及版本信息。
- `Referer`: 标识当前请求是从哪个页面链接过来的（来源页面）。
- `Connection`: 决定当前的底层 TCP 连接在请求完成后是否保持打开（如`keep-alive`）。 

内容协商类：

- `Accept`: 告诉服务器客户端能够处理的媒体类型（MIME 类型），如`text/html`。
- `Accept-Encoding`: 告知服务器客户端⽀持的内容压缩算法，如`gzip`或`br`。
- `Accept-Language`: 告知服务器客户端期望的语言环境，用于实现多语言页面。 
- `Content-Type`: 在 POST 请求中，描述请求体的数据格式（如`application/x-www-form-urlencoded`或`multipart/form-data`）。

```plain
常见的媒体格式类型：
● text/html：HTML格式
● text/plain：纯⽂本格式
● text/xml：XML格式
● image/gif：gif图⽚格式
● image/jpeg：jpg图⽚格式
● image/png：png图⽚格式
表单提交类：
● application/x-www-form-urlencoded：默认的表单提交⽅式，数据被编码为键值对，⽤ & 分隔，如 name=admin&pass=123
● multipart/form-data：⽂件上传
● application/json：JSON 数据，常⽤于 API 接⼝调⽤
```

认证与状态类：

- `Cookie`: HTTP 是“无状态”的，客户端存储并发送给服务器的键值对数据，常用于维持登录状态或追踪用户。
- `Authorization`:用于提供服务器验证身份所需的凭证（如 Basic 认证或 Bearer Token）。安全与特殊类：
- `X-Forwarded-For`:记录请求经过的代理服务器 IP，常用于获取客户端的真实 IP 地址。
- `Origin`: 标识跨域请求（CORS）或 POST 请求的来源，不包含路径信息，仅含协议、域名和端口。

### 4. HTTP 响应

1. HTTP 响应的结构

- 状态行：协议版本、状态码、状态描述
- 响应头：服务器信息、数据类型
- 空行：区分头部和主体
- 响应体：服务器返回的实际数据

1. HTTP 状态码

- 1xx（信息性状态码）：表示接收的请求正在处理。

```plain
100 Continue：请求的初步部分已接收，客户端应继续发送请求。
101 Switching Protocols：服务器同意切换协议。
```

- 2xx（成功状态码）：表示请求正常处理完毕。

```plain
200 OK：请求成功，具体内容取决于 HTTP ⽅法（如 GET、POST）。
201 Created：请求成功并创建了新资源。
204 No Content：请求成功但⽆返回内容。
```

- 3xx（重定向状态码）：需要后续操作才能完成这⼀请求。

```plain
301 Moved Permanently：资源已永久移动到新位置。
302 Found：资源临时移动到新位置。
304 Not Modified：资源未修改，可使⽤缓存版本。
```

- 4xx（客户端错误状态码）：表示请求包含语法错误或无法完成。

```plain
400 Bad Request：请求语法错误或⽆效。
401 Unauthorized：需要身份验证。
403 Forbidden：服务器拒绝请求，客户端⽆权限访问。
404 Not Found：资源未找到。
```

- 5xx（服务器错误状态码）：服务器在处理请求的过程中发生了错误。

```plain
500 Internal Server Error：服务器遇到未知错误。
502 Bad Gateway：⽹关或代理收到⽆效响应。
503 Service Unavailable：服务器暂时不可⽤（如维护或过载）。
504 Gateway Timeout：⽹关超时未收到响应。
```

1. 常见的 HTTP 响应头

| **响应头**                  | **核心作用**   |
| --------------------------- | -------------- |
| Content-Type                | 指定响应体类型 |
| Content-Length              | 响应体长度     |
| Set-Cookie                  | 下发 Cookie    |
| Location                    | 重定向地址     |
| Server                      | 服务器信息     |
| Cache-Control               | 缓存策略       |
| Access-Control-Allow-Origin | 允许跨域来源   |
| X-Frame-Options             | 防点击劫持     |

## (三) HTTP 与 HTTPS

HTTPS（超文本传输安全协议，Hypertext Transfer Protocol Secure）是 HTTP 的安全版本，它在 HTTP 下增加了 SSL/TLS 协议，提供了数据加密、完整性校验和身份验证。HTTPS 通常使用端口 443。

- 身份验证
- 数据加密
- 数据完整性![img](https://cdn.nlark.com/yuque/0/2026/png/65087184/1769681033505-4cd5191a-b7ef-4f87-ab8e-5491038f2a3e.png)


 
