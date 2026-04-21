# 任务
###### 你需要提交以下内容，要求图文结合：
记录工具安装的过程，提交要求题目的 Writeup

记录 linux 搭建的过程，提交 linux 基础命令的学习笔记

学有余力可以继续学习其他内容和知识（如 http 协议、php 基础语法），并提交笔记

[https://markdown.com.cn/basic-syntax/](https://markdown.com.cn/basic-syntax/)

###### 以下工具的安装和使用是本周必须掌握的内容，它们支撑着下一周及后续漏洞的学习
+ 浏览器开发者工具 F12 /查看网页源代码（浏览器自带的，不用下）：最权威的一集。
+ Hackbar: 浏览器插件，能够在页面上直接完成 请求/响应内容编辑，完成各种包括但是不限于伪造的工作。
+ Burp Suite /Yakit： 代理抓包软件，用于 Web 应用程序的渗透测试和攻击，也有爆破等功能
+ dirsearch：目录扫描工具，在使用此工具前，你得先了解一下网页的目录是什么，什么叫对网页目录的 URL 访问（这里就可以借助 AI 了）
+ python3+pip：脚本编写工具
+ sqlmap：自动化 SQL 注入工具
+ 蚁剑： webshell 管理工具
+ Docker：拉镜像，搭靶场

###### 题目
[https://www.nssctf.cn/problem/3412](https://www.nssctf.cn/problem/3412)

[https://www.nssctf.cn/problem/382](https://www.nssctf.cn/problem/382)

[https://www.qsnctf.com/#/main/driving-range?page=1&category=&difficulty=&keyword=robots.txt&user_answer=&user_favorite=&tag_ids=](https://www.qsnctf.com/#/main/driving-range?page=1&category=&difficulty=&keyword=robots.txt&user_answer=&user_favorite=&tag_ids=)

向 AI 询问什么是 GET/POST 请求，可以利用 AI 分析这段简单的php代码是什么意思

###### 你可以使用以下任意方式搭建 linux 环境，这里也需要你自行检索学习搭建方式，并提交搭建过程：
VMware 虚拟机

WSL

服务器平台

linux 系统可以选择装 Kali 或 Ubuntu，不推荐环境不太兼容的 CentOS

[Linux 教程 | 菜鸟教程](https://www.runoob.com/linux/linux-tutorial.html)

[史上最全的Linux常用命令汇总（超全面！超详细！）收藏这一篇就够了！-CSDN博客](https://blog.csdn.net/weixin_44895651/article/details/105289038?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522972f9b1a663c2d6aefefccf5ddd72592%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=972f9b1a663c2d6aefefccf5ddd72592&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_positive~default-1-105289038-null-null.142%5Ev102%5Epc_search_result_base8&utm_term=linux%E5%B8%B8%E7%94%A8%E5%91%BD%E4%BB%A4%E5%A4%A7%E5%85%A8&spm=1018.2226.3001.4187)

[Linux入门教程（非常详细）从零基础入门到精通，看完这一篇就够了_linux学习-CSDN博客](https://blog.csdn.net/bigbangbangbang1/article/details/131575669)

# 前情提要
由于上学期有参加培训，所以工具什么的都有了，本周将在上面基础上再学习一丢丢知识【其实上学期刚开始学的有所遗漏，题目和文章都没看。。。】

## 三道题过一下
### 题目1
#### 题目
[https://www.nssctf.cn/problem/3412](https://www.nssctf.cn/problem/3412)

<font style="color:rgb(51, 51, 51);">什么是HTTP呢？查一查吧 </font><u><font style="color:rgb(51, 51, 51);">https://developer.mozilla.org/zh-CN/docs/Web/HTTP</font></u>  
<font style="color:rgb(51, 51, 51);">在本题中，你需要学习如何发起一个HTTP请求。</font>  
<font style="color:rgb(51, 51, 51);">你可以尝试使用多种工具（如Postman，Python）完成此题。</font>  
<u><font style="color:rgb(51, 51, 51);">https://github.com/XDSEC/moeCTF_2021</font></u>

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/61947449/1776098514591-fe56c6a0-beb5-4842-83c0-fbeaeb14f4ae.png)

#### 解题
<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/61947449/1776098598838-bb7cb97f-fe9a-4fe6-9da3-e74ec7336a06.png)

### 题目2
#### 题目
[https://www.nssctf.cn/problem/382](https://www.nssctf.cn/problem/382)

<font style="color:rgb(51, 51, 51);">flag以NSSCTF{}形式提交</font>

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/61947449/1776098749219-6814ccbd-eecc-44cc-b9e5-8b69a8fc4844.png)

#### 解题【个人竟然没有写出来！！呃呃】
##### 错解
看题非常显而易见的，用post把时间改掉【不是】

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/61947449/1776099185216-6a7c4fb4-ea17-4f5e-aaed-9f1be7a2c0cd.png)<font style="color:rgb(31, 31, 31);">看这里格式：date  Mon, 13 Apr 2026 16:48:23 GMT</font>

<font style="color:rgb(31, 31, 31);">【根据计算，应该是2021.10.23】</font>

<font style="color:rgb(35, 35, 38);">Sat, 23 Oct 2021 00:00:00 GMT</font>

##### <font style="color:rgb(35, 35, 38);">正解</font>
<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/61947449/1776099455489-8a547905-ee48-4763-820d-b8b676c60b99.png)就在代码审计里

### 题目3
#### 题目
[https://www.qsnctf.com/#/main/driving-range?page=1&category=&difficulty=&keyword=robots.txt&user_answer=&user_favorite=&tag_ids=&challenge_id=902](https://www.qsnctf.com/#/main/driving-range?page=1&category=&difficulty=&keyword=robots.txt&user_answer=&user_favorite=&tag_ids=&challenge_id=902)

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/61947449/1776099756896-33bf7750-5bc9-4bdd-8080-6ff8d8e8f558.png)

#### 解题
+ 先把url改了，后缀/robots.txt【猜测，因为他没有说正确的配置要求是什么】

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/61947449/1776100034196-6f29fa5f-8910-4f45-8214-78403ec8aed8.png)看见这个

+ 三个url改过来，，在/secret.php

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/61947449/1776100183202-637f59ab-2785-43dc-8aee-19e996724ece.png)找到了，输入即可

+ <!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/61947449/1776100286001-c1266ced-ad76-403a-b400-c7e5914671e2.png)

## 工具
<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/61947449/1776171950645-9316ed6e-3d1d-4347-b3a4-e6f1efaef030.png)<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/61947449/1776171980915-52214ff7-3de5-4ff5-beba-42e1a9aee9b9.png)

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/61947449/1776172049864-7d0a2236-cd6a-42f6-b4f4-5b5d0db6132d.png)<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/61947449/1776171997097-60423ff7-1fa4-405c-a4cd-b682e3d1dd59.png)

这是目前所有的工具了。。。

# 知识点学习
## markdown语法
来源：[https://markdown.com.cn/basic-syntax/](https://markdown.com.cn/basic-syntax/)

[https://markdown.com.cn/editor/](https://markdown.com.cn/editor/)markdown在线编译器

### 标题语法
| <font style="color:rgb(44, 62, 80);">Markdown语法</font> | <font style="color:rgb(44, 62, 80);">HTML</font> | <font style="color:rgb(44, 62, 80);">预览效果</font> |
| --- | --- | --- |
| `<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);"># Heading level 1</font>` | `<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);"><h1>Heading level 1</h1></font>` | # <font style="color:rgb(44, 62, 80);">Heading level 1</font> |
| `<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">## Heading level 2</font>` | `<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);"><h2>Heading level 2</h2></font>` | ## <font style="color:rgb(44, 62, 80);">Heading level 2</font> |
| `<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">### Heading level 3</font>` | `<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);"><h3>Heading level 3</h3></font>` | ### <font style="color:rgb(44, 62, 80);">Heading level 3</font> |
| `<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">#### Heading level 4</font>` | `<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);"><h4>Heading level 4</h4></font>` | #### <font style="color:rgb(44, 62, 80);">Heading level 4</font> |
| `<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">##### Heading level 5</font>` | `<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);"><h5>Heading level 5</h5></font>` | ##### <font style="color:rgb(44, 62, 80);">Heading level 5</font> |
| `<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">###### Heading level 6</font>` | `<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);"><h6>Heading level 6</h6></font>` | ###### <font style="color:rgb(44, 62, 80);">Heading level 6</font> |


<font style="color:rgb(44, 62, 80);">#的个数代码标题的号，<h?></h?></font>

<font style="color:rgb(44, 62, 80);">【</font>`<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">#</font>`<font style="color:rgb(44, 62, 80);"> 和标题之间进行分隔】</font>

<font style="color:rgb(44, 62, 80);">【选择：====做底，是一级标题，------做底，是二级标题】</font>

### <font style="color:rgb(44, 62, 80);">段落语法</font>
<font style="color:rgb(44, 62, 80);">使用</font>**<font style="color:rgb(44, 62, 80);">空白行</font>**<font style="color:rgb(44, 62, 80);">将一行或多行文本进行分隔</font>

| <font style="color:rgb(44, 62, 80);">Markdown语法</font> | <font style="color:rgb(44, 62, 80);">HTML</font> | <font style="color:rgb(44, 62, 80);">预览效果</font> |
| --- | --- | --- |
| `<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">I really like using Markdown.      </font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">I think I'll use it to format all of my documents from now on.</font>` | `<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);"><p>I really like using Markdown.</p>      </font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);"><p>I think I'll use it to format all of my documents from now on.</p></font>` | <font style="color:rgb(44, 62, 80);">I really like using Markdown.</font><br/><font style="color:rgb(44, 62, 80);">I think I'll use it to format all of my documents from now on.</font> |


### <font style="color:rgb(44, 62, 80);">换行语法</font>
<font style="color:rgb(44, 62, 80);">在一行的末尾添加两个或多个空格，然后按回车键,即可创建一个换行(</font>`<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);"><br></font>`<font style="color:rgb(44, 62, 80);">)</font>

| <font style="color:rgb(44, 62, 80);">Markdown语法</font> | <font style="color:rgb(44, 62, 80);">HTML</font> | <font style="color:rgb(44, 62, 80);">预览效果</font> |
| --- | --- | --- |
| `<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">This is the first line.     </font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">And this is the second line.</font>` | `<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);"><p>This is the first line.<br>   </font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">And this is the second line.</p></font>` | <font style="color:rgb(44, 62, 80);">This is the first line.   </font><font style="color:rgb(44, 62, 80);">And this is the second line.</font> |


<p></p>

### <font style="color:rgb(44, 62, 80);">强调语法</font>
#### 黑体
<font style="color:rgb(44, 62, 80);">要加粗文本，请在单词或短语的前后各添加两个</font>**<font style="color:rgb(44, 62, 80);">星号</font>**<font style="color:rgb(44, 62, 80);">（asterisks）或</font>**<font style="color:rgb(44, 62, 80);">下划线</font>**<font style="color:rgb(44, 62, 80);">（underscores）。</font>

<font style="color:rgb(44, 62, 80);">如需加粗一个单词或短语的中间部分用以表示强调的话，请在要加粗部分的两侧各添加两个星号。</font>

| <font style="color:rgb(44, 62, 80);">Markdown语法</font> | <font style="color:rgb(44, 62, 80);">HTML</font> | <font style="color:rgb(44, 62, 80);">预览效果</font> |
| --- | --- | --- |
| `<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">I just love </font>`<br/>`<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">**bold text**.</font>` | `<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">I just love <strong>bold text</strong>.</font>` | <font style="color:rgb(44, 62, 80);">I just love</font><font style="color:rgb(44, 62, 80);"> </font>**<font style="color:rgb(44, 62, 80);">bold text</font>**<font style="color:rgb(44, 62, 80);">.</font> |
| `<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">I just love </font>`<br/>`<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">__bold text__.</font>` | `<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">I just love <strong>bold text</strong>.</font>` | <font style="color:rgb(44, 62, 80);">I just love</font><font style="color:rgb(44, 62, 80);"> </font>**<font style="color:rgb(44, 62, 80);">bold text</font>**<font style="color:rgb(44, 62, 80);">.</font> |
| `<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">Love**is**bold</font>` | `<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">Love<strong>is</strong>bold</font>` | <font style="color:rgb(44, 62, 80);">Love</font>**<font style="color:rgb(44, 62, 80);">is</font>**<font style="color:rgb(44, 62, 80);">bold</font> |


<font style="color:rgb(44, 62, 80);"><strong></strong></font>

<font style="color:rgb(44, 62, 80);">【</font>`<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">Love__is__bold</font>`<font style="color:rgb(71, 101, 130);">不行，格式兼容问题</font><font style="color:rgb(44, 62, 80);">】</font>

#### <font style="color:rgb(44, 62, 80);">斜体</font>
<font style="color:rgb(44, 62, 80);">请在单词或短语前后添加一个星号或下划线。</font>

<font style="color:rgb(44, 62, 80);">要斜体突出单词的中间部分，请在字母前后各添加一个星号，中间不要带空格</font>

| <font style="color:rgb(44, 62, 80);">Markdown语法</font> | <font style="color:rgb(44, 62, 80);">HTML</font> | <font style="color:rgb(44, 62, 80);">预览效果</font> |
| --- | --- | --- |
| `<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">Italicized text is the *cat's meow*.</font>` | `<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">Italicized text is the <em>cat's meow</em>.</font>` | <font style="color:rgb(44, 62, 80);">Italicized text is the</font><font style="color:rgb(44, 62, 80);"> </font>_<font style="color:rgb(44, 62, 80);">cat’s meow</font>_<font style="color:rgb(44, 62, 80);">.</font> |
| `<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">Italicized text is the _cat's meow_.</font>` | `<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">Italicized text is the <em>cat's meow</em>.</font>` | <font style="color:rgb(44, 62, 80);">Italicized text is the</font><font style="color:rgb(44, 62, 80);"> </font>_<font style="color:rgb(44, 62, 80);">cat’s meow</font>_<font style="color:rgb(44, 62, 80);">.</font> |
| `<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">A*cat*meow</font>` | `<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">A<em>cat</em>meow</font>` | <font style="color:rgb(44, 62, 80);">A</font>_<font style="color:rgb(44, 62, 80);">cat</font>_<font style="color:rgb(44, 62, 80);">meow</font> |


<font style="color:rgb(44, 62, 80);"><em></em></font>

#### <font style="color:rgb(44, 62, 80);">粗体和斜体</font>
<font style="color:rgb(44, 62, 80);">【注意：黑体**A**,斜体*A*】</font>

| <font style="color:rgb(44, 62, 80);">Markdown语法</font> | <font style="color:rgb(44, 62, 80);">HTML</font> | <font style="color:rgb(44, 62, 80);">预览效果</font> |
| --- | --- | --- |
| `<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">This text is ***really important***.</font>` | `<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">This text is <strong><em>really important</em></strong>.</font>` | <font style="color:rgb(44, 62, 80);">This text is</font><font style="color:rgb(44, 62, 80);"> </font>_**<font style="color:rgb(44, 62, 80);">really important</font>**_<font style="color:rgb(44, 62, 80);">.</font> |
| `<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">This text is ___really important___.</font>` | `<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">This text is <strong><em>really important</em></strong>.</font>` | <font style="color:rgb(44, 62, 80);">This text is</font><font style="color:rgb(44, 62, 80);"> </font>_**<font style="color:rgb(44, 62, 80);">really important</font>**_<font style="color:rgb(44, 62, 80);">.</font> |
| `<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">This text is __*really important*__.</font>` | `<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">This text is <strong><em>really important</em></strong>.</font>` | <font style="color:rgb(44, 62, 80);">This text is</font><font style="color:rgb(44, 62, 80);"> </font>_**<font style="color:rgb(44, 62, 80);">really important</font>**_<font style="color:rgb(44, 62, 80);">.</font> |
| `<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">This text is **_really important_**.</font>` | `<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">This text is <strong><em>really important</em></strong>.</font>` | <font style="color:rgb(44, 62, 80);">This text is</font><font style="color:rgb(44, 62, 80);"> </font>_**<font style="color:rgb(44, 62, 80);">really important</font>**_<font style="color:rgb(44, 62, 80);">.</font> |
| `<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">This is really***very***important text.</font>` | `<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">This is really<strong><em>very</em></strong>important text.</font>` | <font style="color:rgb(44, 62, 80);">This is really</font>_**<font style="color:rgb(44, 62, 80);">very</font>**_<font style="color:rgb(44, 62, 80);">important text.</font> |


### <font style="color:rgb(44, 62, 80);">引用语法</font>
<font style="color:rgb(44, 62, 80);">要创建块引用，请在</font><font style="color:rgb(44, 62, 80);background-color:#FBDE28;">段落前添加一个 </font>`<font style="color:rgb(71, 101, 130);background-color:#FBDE28;">></font>`<font style="color:rgb(44, 62, 80);background-color:#FBDE28;"> 符号</font><font style="color:rgb(44, 62, 80);">。</font>

```plain
> Dorothy followed her through many of the beautiful rooms in her castle.
```

<font style="color:rgb(44, 62, 80);">渲染效果如下所示：</font>

<font style="color:rgb(153, 153, 153);">Dorothy followed her through many of the beautiful rooms in her castle.</font>

###### <font style="color:rgb(44, 62, 80);">多个段落的块引用</font>
<font style="color:rgb(44, 62, 80);">块引用可以包含多个段落。为段落之间的空白行添加一个</font><font style="color:rgb(44, 62, 80);"> </font>`<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">></font>`<font style="color:rgb(44, 62, 80);"> </font><font style="color:rgb(44, 62, 80);">符号。</font>

```plain
> Dorothy followed her through many of the beautiful rooms in her castle.
>
> The Witch bade her clean the pots and kettles and sweep the floor and keep the fire fed with wood.
```

<font style="color:rgb(44, 62, 80);">渲染效果如下：</font>

<font style="color:rgb(153, 153, 153);">Dorothy followed her through many of the beautiful rooms in her castle.</font>

<font style="color:rgb(153, 153, 153);">The Witch bade her clean the pots and kettles and sweep the floor and keep the fire fed with wood.</font>

###### <font style="color:rgb(44, 62, 80);">嵌套块引用</font>
<font style="color:rgb(44, 62, 80);">块引用可以嵌套。在要嵌套的段落前添加一个</font><font style="color:rgb(44, 62, 80);"> </font>`<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">>></font>`<font style="color:rgb(44, 62, 80);"> </font><font style="color:rgb(44, 62, 80);">符号。</font>

```plain
> Dorothy followed her through many of the beautiful rooms in her castle.
>
>> The Witch bade her clean the pots and kettles and sweep the floor and keep the fire fed with wood.
```

<font style="color:rgb(44, 62, 80);">渲染效果如下：</font>

<font style="color:rgb(153, 153, 153);">Dorothy followed her through many of the beautiful rooms in her castle.</font>

<font style="color:rgb(153, 153, 153);">The Witch bade her clean the pots and kettles and sweep the floor and keep the fire fed with wood.</font>

###### <font style="color:rgb(44, 62, 80);">带有其它元素的块引用</font>
<font style="color:rgb(44, 62, 80);">块引用可以包含其他 Markdown 格式的元素。并非所有元素都可以使用，你需要进行实验以查看哪些元素有效。</font>

```plain
> #### The quarterly results look great!
>
> - Revenue was off the chart.
> - Profits were higher than ever.
>
>  *Everything* is going according to **plan**.
```

<font style="color:rgb(44, 62, 80);">渲染效果如下：</font>

#### <font style="color:rgb(153, 153, 153);">The quarterly results look great!</font>
+ <font style="color:rgb(153, 153, 153);">Revenue was off the chart.</font>
+ <font style="color:rgb(153, 153, 153);">Profits were higher than ever.</font>

_<font style="color:rgb(153, 153, 153);">Everything</font>_<font style="color:rgb(153, 153, 153);"> is going according to </font>**<font style="color:rgb(153, 153, 153);">plan</font>**<font style="color:rgb(153, 153, 153);">.</font>

### 列表语法
<font style="color:rgb(44, 62, 80);">可以将多个条目组织成有序或无序列表。</font>

#### <font style="color:rgb(44, 62, 80);">有序列表</font>
<font style="color:rgb(44, 62, 80);">每个列表项前添加数字并紧跟一个英文句点【必须从数字1开始，但是不用按顺序】</font>

| <font style="color:rgb(44, 62, 80);">Markdown语法</font> | <font style="color:rgb(44, 62, 80);">HTML</font> | <font style="color:rgb(44, 62, 80);">预览效果</font> |
| --- | --- | --- |
| `<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">1. First item   </font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">2. Second item   </font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">3. Third item   </font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">4. Fourth item</font>` | `<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);"><ol>   </font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);"><li>First item</li>   </font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);"><li>Second item</li>   </font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);"><li>Third item</li>   </font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);"><li>Fourth item</li>   </font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);"></ol></font>` | 1. <font style="color:rgb(44, 62, 80);">First item</font><br/>2. <font style="color:rgb(44, 62, 80);">Second item</font><br/>3. <font style="color:rgb(44, 62, 80);">Third item</font><br/>4. <font style="color:rgb(44, 62, 80);">Fourth item</font> |
| `<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">1. First item   </font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">1. Second item   </font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">1. Third item   </font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">1. Fourth item</font>` | `<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);"><ol>   </font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);"><li>First item</li>   </font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);"><li>Second item</li>   </font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);"><li>Third item</li>   </font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);"><li>Fourth item</li>   </font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);"></ol></font>` | 1. <font style="color:rgb(44, 62, 80);">First item</font><br/>2. <font style="color:rgb(44, 62, 80);">Second item</font><br/>3. <font style="color:rgb(44, 62, 80);">Third item</font><br/>4. <font style="color:rgb(44, 62, 80);">Fourth item</font> |
| `<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">1. First item   </font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">8. Second item   </font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">3. Third item   </font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">5. Fourth item</font>` | `<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);"><ol>   </font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);"><li>First item</li>   </font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);"><li>Second item</li>   </font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);"><li>Third item</li>   </font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);"><li>Fourth item</li>   </font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);"></ol></font>` | 1. <font style="color:rgb(44, 62, 80);">First item</font><br/>2. <font style="color:rgb(44, 62, 80);">Second item</font><br/>3. <font style="color:rgb(44, 62, 80);">Third item</font><br/>4. <font style="color:rgb(44, 62, 80);">Fourth item</font> |
| `<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">1. First item   </font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">2. Second item   </font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">3. Third item   </font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">1. Indented item   </font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">2. Indented item   </font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">4. Fourth item</font>` | `<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);"><ol>   </font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);"><li>First item</li>   </font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);"><li>Second item</li>   </font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);"><li>Third item   </font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);"><ol>   </font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);"><li>Indented item</li>   </font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);"><li>Indented item</li>   </font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);"></ol>   </font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);"></li>   </font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);"><li>Fourth item</li>   </font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);"></ol></font>` | 1. <font style="color:rgb(44, 62, 80);">First item</font><br/>2. <font style="color:rgb(44, 62, 80);">Second item</font><br/>3. <font style="color:rgb(44, 62, 80);">Third item</font><br/>    1. <font style="color:rgb(44, 62, 80);">Indented item</font><br/>    2. <font style="color:rgb(44, 62, 80);">Indented item</font><br/>4. <font style="color:rgb(44, 62, 80);">Fourth item</font> |


<ol></ol>

#### <font style="color:rgb(44, 62, 80);">无序列表</font>
<font style="color:rgb(44, 62, 80);">请在每个列表项前面添加破折号 (-)、星号 (*) 或加号 (+) 。</font>

<font style="color:rgb(44, 62, 80);">缩进一个或多个列表项可创建嵌套列表。</font>

| <font style="color:rgb(44, 62, 80);">Markdown语法</font> | <font style="color:rgb(44, 62, 80);">HTML</font> | <font style="color:rgb(44, 62, 80);">预览效果</font> |
| --- | --- | --- |
| `<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">- First item   </font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">- Second item   </font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">- Third item   </font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">- Fourth item</font>` | `<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);"><ul>   </font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);"><li>First item</li>   </font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);"><li>Second item</li>   </font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);"><li>Third item</li>   </font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);"><li>Fourth item</li>   </font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);"></ul></font>` | + <font style="color:rgb(44, 62, 80);">First item</font><br/>+ <font style="color:rgb(44, 62, 80);">Second item</font><br/>+ <font style="color:rgb(44, 62, 80);">Third item</font><br/>+ <font style="color:rgb(44, 62, 80);">Fourth item</font> |
| `<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">* First item   </font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">* Second item   </font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">* Third item   </font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">* Fourth item</font>` | `<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);"><ul>   </font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);"><li>First item</li>   </font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);"><li>Second item</li>   </font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);"><li>Third item</li>   </font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);"><li>Fourth item</li>   </font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);"></ul></font>` | + <font style="color:rgb(44, 62, 80);">First item</font><br/>+ <font style="color:rgb(44, 62, 80);">Second item</font><br/>+ <font style="color:rgb(44, 62, 80);">Third item</font><br/>+ <font style="color:rgb(44, 62, 80);">Fourth item</font> |
| `<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">+ First item   </font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">+ Second item   </font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">+ Third item   </font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">+ Fourth item</font>` | `<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);"><ul>   </font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);"><li>First item</li>   </font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);"><li>Second item</li>   </font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);"><li>Third item</li>   </font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);"><li>Fourth item</li>   </font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);"></ul></font>` | + <font style="color:rgb(44, 62, 80);">First item</font><br/>+ <font style="color:rgb(44, 62, 80);">Second item</font><br/>+ <font style="color:rgb(44, 62, 80);">Third item</font><br/>+ <font style="color:rgb(44, 62, 80);">Fourth item</font> |
| `<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">- First item   </font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">- Second item   </font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">- Third item   </font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">- Indented item   </font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">- Indented item   </font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">- Fourth item</font>` | `<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);"><ul>   </font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);"><li>First item</li>   </font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);"><li>Second item</li>   </font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);"><li>Third item   </font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);"><ul>   </font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);"><li>Indented item</li>   </font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);"><li>Indented item</li>   </font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);"></ul>   </font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);"></li>   </font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);"><li>Fourth item</li>   </font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);"></ul></font>` | + <font style="color:rgb(44, 62, 80);">First item</font><br/>+ <font style="color:rgb(44, 62, 80);">Second item</font><br/>+ <font style="color:rgb(44, 62, 80);">Third item</font><br/>    - <font style="color:rgb(44, 62, 80);">Indented item</font><br/>    - <font style="color:rgb(44, 62, 80);">Indented item</font><br/>+ <font style="color:rgb(44, 62, 80);">Fourth item</font> |


<font style="color:rgb(44, 62, 80);"><ul></ul></font>

### <font style="color:rgb(44, 62, 80);">代码语法</font>
<font style="color:rgb(44, 62, 80);">要将单词或短语表示为代码，请将其包裹在反引号 (</font>`<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">`</font>`<font style="color:rgb(44, 62, 80);">) 中。</font>

| <font style="color:rgb(44, 62, 80);">Markdown语法</font> | <font style="color:rgb(44, 62, 80);">HTML</font> | <font style="color:rgb(44, 62, 80);">预览效果</font> |
| --- | --- | --- |
| `<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">At the command prompt, </font>`<br/>`<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">type `nano`.</font>` | `<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">At the command prompt, type <code>nano</code>.</font>` | <font style="color:rgb(44, 62, 80);">At the command prompt, type</font><font style="color:rgb(44, 62, 80);"> </font>`<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">nano</font>`<br/><font style="color:rgb(44, 62, 80);">.</font> |


#### <font style="color:rgb(44, 62, 80);">转义反引号</font>
<font style="color:rgb(44, 62, 80);">如果你要表示为代码的单词或短语中包含一个或多个反引号，则可以通过将单词或短语包裹在双反引号</font>

<font style="color:rgb(44, 62, 80);">(</font>`<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">``</font>`<font style="color:rgb(44, 62, 80);">)中。</font>

| <font style="color:rgb(44, 62, 80);">Markdown语法</font> | <font style="color:rgb(44, 62, 80);">HTML</font> | <font style="color:rgb(44, 62, 80);">预览效果</font> |
| --- | --- | --- |
| `<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">``Use `code` in your Markdown file.``</font>` | `<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);"><code>Use `code` in your Markdown file.</code></font>` | `<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">Use `code` in your Markdown file.</font>` |


#### <font style="color:rgb(44, 62, 80);">代码块</font>
<font style="color:rgb(44, 62, 80);">要创建代码块，请将代码块的每一行缩进至少四个空格或一个制表符。</font>

### <font style="color:rgb(44, 62, 80);">分割线语法</font>
<font style="color:rgb(44, 62, 80);">要创建分隔线，请在单独一行上使用三个或多个星号 (</font>`<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">***</font>`<font style="color:rgb(44, 62, 80);">)、破折号 (</font>`<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">---</font>`<font style="color:rgb(44, 62, 80);">) 或下划线</font>

<font style="color:rgb(44, 62, 80);"> (</font>`<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">___</font>`<font style="color:rgb(44, 62, 80);">) ，并且不能包含其他内容。</font>

```plain
***

---

_________________
```

【<font style="color:rgb(44, 62, 80);">为了兼容性，请在分隔线的前后均</font><font style="color:rgb(44, 62, 80);background-color:#FBDE28;">添加空白行</font><font style="color:rgb(44, 62, 80);">。</font>】

### 链接语法
<font style="color:rgb(44, 62, 80);">链接文本放在中括号内，链接地址放在后面的括号中，链接title可选。</font>

<font style="color:rgb(44, 62, 80);">超链接Markdown语法代码：</font>`<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">[超链接显示名](超链接地址</font><font style="color:rgb(71, 101, 130);background-color:#FBDE28;"> </font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">"超链接title")</font>`

<font style="color:rgb(44, 62, 80);">对应的HTML代码：</font>`<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);"><a href="超链接地址" title="超链接title">超链接显示名</a></font>`

```plain
这是一个链接 [Markdown语法](https://markdown.com.cn)。
```

<font style="color:rgb(44, 62, 80);">渲染效果如下：</font>

<font style="color:rgb(44, 62, 80);">这是一个链接</font><font style="color:rgb(44, 62, 80);"> </font>[<font style="color:rgb(62, 175, 124);">Markdown语法(opens new window)</font>](https://markdown.com.cn/)<font style="color:rgb(44, 62, 80);">。</font>

#### <font style="color:rgb(44, 62, 80);">给链接增加 Title</font>
<font style="color:rgb(44, 62, 80);">链接title是当鼠标悬停在链接上时会出现的文字，这个title是可选的，它放在圆括号中链接地址后面，跟链接地址之间以</font><font style="color:rgb(44, 62, 80);background-color:#FBDE28;">空格分隔</font><font style="color:rgb(44, 62, 80);">。</font>

```plain
这是一个链接 [Markdown语法](https://markdown.com.cn "最好的markdown教程")。
```

<font style="color:rgb(44, 62, 80);">渲染效果如下：</font>

<font style="color:rgb(44, 62, 80);">这是一个链接</font><font style="color:rgb(44, 62, 80);"> </font>[<font style="color:rgb(62, 175, 124);">Markdown语法(opens new window)</font>](https://markdown.com.cn/)<font style="color:rgb(44, 62, 80);">。</font>

#### <font style="color:rgb(44, 62, 80);">网址和Email地址</font>
<font style="color:rgb(44, 62, 80);">使用</font><font style="color:rgb(44, 62, 80);background-color:#FBDE28;">尖括号</font><font style="color:rgb(44, 62, 80);">可以很方便地把URL或者email地址变成可点击的链接。</font>

```plain
<https://markdown.com.cn>
<fake@example.com>
```

<font style="color:rgb(44, 62, 80);">渲染效果如下：</font>

[<font style="color:rgb(62, 175, 124);">https://markdown.com.cn(opens new window)</font>](https://markdown.com.cn/)<font style="color:rgb(44, 62, 80);">  
</font>[<font style="color:rgb(62, 175, 124);">fake@example.com</font>](mailto:fake@example.com)

#### <font style="color:rgb(44, 62, 80);">带格式化的链接</font>
[<font style="color:rgb(62, 175, 124);">强调</font>](https://markdown.com.cn/basic-syntax/links.html#emphasis)<font style="color:rgb(44, 62, 80);"> </font><font style="color:rgb(44, 62, 80);">链接, 在链接语法前后增加星号。 </font>

<font style="color:rgb(44, 62, 80);">要将链接表示为代码，请在方括号中添加反引号。</font>

```plain
I love supporting the **[EFF](https://eff.org)**.
This is the *[Markdown Guide](https://www.markdownguide.org)*.
See the section on [`code`](#code).
```

<font style="color:rgb(44, 62, 80);">渲染效果如下：</font>

<font style="color:rgb(44, 62, 80);">I love supporting the</font><font style="color:rgb(44, 62, 80);"> </font>[**<font style="color:rgb(62, 175, 124);">EFF(opens new window)</font>**](https://eff.org/)<font style="color:rgb(44, 62, 80);">.  
</font><font style="color:rgb(44, 62, 80);">This is the</font><font style="color:rgb(44, 62, 80);"> </font>[_<font style="color:rgb(62, 175, 124);">Markdown Guide(opens new window)</font>_](https://www.markdownguide.org/)<font style="color:rgb(44, 62, 80);">.  
</font><font style="color:rgb(44, 62, 80);">See the section on</font><font style="color:rgb(44, 62, 80);"> </font>[<font style="color:rgb(62, 175, 124);">code</font>](https://markdown.com.cn/basic-syntax/links.html#code)<font style="color:rgb(44, 62, 80);">.</font>

#### <font style="color:rgb(44, 62, 80);">引用类型链接</font>
<font style="color:rgb(44, 62, 80);">引用样式链接是一种特殊的链接，它使URL在Markdown中</font><font style="color:rgb(44, 62, 80);background-color:#FBDE28;">更易于显示和阅读</font><font style="color:rgb(44, 62, 80);">。</font>

<font style="color:rgb(44, 62, 80);">参考样式链接分为两部分：与文本保持</font>**<font style="color:rgb(44, 62, 80);">内联</font>**<font style="color:rgb(44, 62, 80);">的部分以及存储在文件中</font>**<font style="color:rgb(44, 62, 80);">其他位置</font>**<font style="color:rgb(44, 62, 80);">的部分，以使文本易于阅读。</font>

##### <font style="color:rgb(44, 62, 80);">链接的第一部分格式</font>
<font style="color:rgb(44, 62, 80);">引用类型的链接的第一部分使用两组括号进行格式设置。</font>

<font style="color:rgb(44, 62, 80);">第一组方括号包围应显示为链接的</font><font style="color:rgb(44, 62, 80);background-color:#FDE6D3;">文本</font><font style="color:rgb(44, 62, 80);">。第二组括号显示了一个</font><font style="color:rgb(44, 62, 80);background-color:#FDE6D3;">标签</font><font style="color:rgb(44, 62, 80);">，该标签用于指向您存储在文档其他位置的链接。</font>

<font style="color:rgb(44, 62, 80);">尽管不是必需的，可以在第一组和第二组括号之间包含一个空格。第二组括号中的标签不区分大小写，可以包含字母，数字，空格或标点符号。</font>

<font style="color:rgb(44, 62, 80);">以下示例格式对于链接的第一部分效果相同：</font>

+ `<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">[hobbit-hole][1]</font>`
+ `<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">[hobbit-hole]</font><font style="color:rgb(71, 101, 130);background-color:#FDE6D3;"> </font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">[1]</font>`

##### <font style="color:rgb(44, 62, 80);">链接的第二部分格式</font>
<font style="color:rgb(44, 62, 80);">引用类型链接的第二部分使用以下属性设置格式：</font>

1. <font style="color:rgb(44, 62, 80);">放在括号中的标签，其后紧跟一个冒号和至少一个空格（例如</font>`<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">[label]:</font>`<font style="color:rgb(44, 62, 80);">）。</font>
2. <font style="color:rgb(44, 62, 80);">链接的URL，可以选择将其括在</font><font style="color:rgb(44, 62, 80);background-color:#FDE6D3;">尖括号</font><font style="color:rgb(44, 62, 80);">中。</font>
3. <font style="color:rgb(44, 62, 80);">链接的可选标题，可以将其括在</font><font style="color:rgb(44, 62, 80);background-color:#FDE6D3;">双引号，单引号或括号</font><font style="color:rgb(44, 62, 80);">中。</font>

<font style="color:rgb(44, 62, 80);">以下示例格式对于链接的第二部分效果相同：</font>

+ `<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">[1]: https://en.wikipedia.org/wiki/Hobbit#Lifestyle</font>`
+ `<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">[1]: https://en.wikipedia.org/wiki/Hobbit#Lifestyle "Hobbit lifestyles"</font>`
+ `<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">[1]: https://en.wikipedia.org/wiki/Hobbit#Lifestyle 'Hobbit lifestyles'</font>`
+ `<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">[1]: https://en.wikipedia.org/wiki/Hobbit#Lifestyle (Hobbit lifestyles)</font>`
+ `<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">[1]: <https://en.wikipedia.org/wiki/Hobbit#Lifestyle> "Hobbit lifestyles"</font>`
+ `<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">[1]: <https://en.wikipedia.org/wiki/Hobbit#Lifestyle> 'Hobbit lifestyles'</font>`
+ `<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">[1]: <https://en.wikipedia.org/wiki/Hobbit#Lifestyle> (Hobbit lifestyles)</font>`

<font style="color:rgb(44, 62, 80);">可以将链接的第二部分放在Markdown文档中的任何位置。有些人将它们放在出现的段落之后，有些人则将它们放在文档的末尾（例如尾注或脚注）。</font>

### <font style="color:rgb(44, 62, 80);">图片语法</font>
<font style="color:rgb(44, 62, 80);">要添加图像，请使用感叹号 (</font>`<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">!</font>`<font style="color:rgb(44, 62, 80);">), 然后在方括号增加替代文本，图片链接放在圆括号里，括号里的链接后可以增加一个可选的图片标题文本。</font>

<font style="color:rgb(44, 62, 80);">插入图片Markdown语法代码：</font>`<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">![图片alt](图片链接 "图片title")</font>`<font style="color:rgb(44, 62, 80);">。</font>

<font style="color:rgb(44, 62, 80);">对应的HTML代码：</font>`<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);"><img src="图片链接" alt="图片alt" title="图片title"></font>`

```plain
![这是图片](/assets/img/philly-magic-garden.jpg "Magic Gardens")
```

<font style="color:rgb(44, 62, 80);">给图片增加链接，请将图像的Markdown 括在方括号中，然后将链接添加在圆括号中。</font>

```plain
[![沙漠中的岩石图片](/assets/img/shiprock.jpg "Shiprock")](https://markdown.com.cn)
```

### 转义字符语法
#### <font style="color:rgb(44, 62, 80);">可做转义的字符</font>
<font style="color:rgb(44, 62, 80);">以下列出的字符都可以通过使用</font><font style="color:rgb(44, 62, 80);background-color:#FDE6D3;">反斜杠字符</font><font style="color:rgb(44, 62, 80);">从而达到转义目的。</font>

| <font style="color:rgb(44, 62, 80);">Character</font> | <font style="color:rgb(44, 62, 80);">Name</font> |
| --- | --- |
| <font style="color:rgb(44, 62, 80);">\</font> | <font style="color:rgb(44, 62, 80);">backslash</font> |
| <font style="color:rgb(44, 62, 80);">`</font> | <font style="color:rgb(44, 62, 80);">backtick (see also </font>[<font style="color:rgb(62, 175, 124);">escaping backticks in code</font>](https://markdown.com.cn/basic-syntax/escaping-characters.html#escaping-backticks)<font style="color:rgb(44, 62, 80);">)</font> |
| <font style="color:rgb(44, 62, 80);">*</font> | <font style="color:rgb(44, 62, 80);">asterisk</font> |
| <font style="color:rgb(44, 62, 80);">_</font> | <font style="color:rgb(44, 62, 80);">underscore</font> |
| <font style="color:rgb(44, 62, 80);">{ }</font> | <font style="color:rgb(44, 62, 80);">curly braces</font> |
| <font style="color:rgb(44, 62, 80);">[ ]</font> | <font style="color:rgb(44, 62, 80);">brackets</font> |
| <font style="color:rgb(44, 62, 80);">( )</font> | <font style="color:rgb(44, 62, 80);">parentheses</font> |
| <font style="color:rgb(44, 62, 80);">#</font> | <font style="color:rgb(44, 62, 80);">pound sign</font> |
| <font style="color:rgb(44, 62, 80);">+</font> | <font style="color:rgb(44, 62, 80);">plus sign</font> |
| <font style="color:rgb(44, 62, 80);">-</font> | <font style="color:rgb(44, 62, 80);">minus sign (hyphen)</font> |
| <font style="color:rgb(44, 62, 80);">.</font> | <font style="color:rgb(44, 62, 80);">dot</font> |
| <font style="color:rgb(44, 62, 80);">!</font> | <font style="color:rgb(44, 62, 80);">exclamation mark</font> |
| <font style="color:rgb(44, 62, 80);">|</font> | <font style="color:rgb(44, 62, 80);">pipe (see also </font>[<font style="color:rgb(62, 175, 124);">escaping pipe in tables</font>](https://markdown.com.cn/extended-syntax/escaping-pipe-characters-in-tables.html)<font style="color:rgb(44, 62, 80);">)</font> |


#### <font style="color:rgb(44, 62, 80);">特殊字符自动转义 </font>
<font style="color:rgb(44, 62, 80);">在 HTML 文件中，有两个字符需要特殊处理：</font><font style="color:rgb(44, 62, 80);"> </font>`<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);"><</font>`<font style="color:rgb(44, 62, 80);"> </font><font style="color:rgb(44, 62, 80);">和</font><font style="color:rgb(44, 62, 80);"> </font>`<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">&</font>`<font style="color:rgb(44, 62, 80);"> </font><font style="color:rgb(44, 62, 80);">。</font><font style="color:rgb(44, 62, 80);"> </font>

`<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);"><</font>`<font style="color:rgb(44, 62, 80);"> 符号用于</font><font style="color:rgb(44, 62, 80);background-color:#FDE6D3;">起始标签</font><font style="color:rgb(44, 62, 80);">，</font>

`<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">&</font>`<font style="color:rgb(44, 62, 80);"> 符号则用于</font><font style="color:rgb(44, 62, 80);background-color:#FDE6D3;">标记 HTML 实体</font><font style="color:rgb(44, 62, 80);">，</font>

<font style="color:rgb(44, 62, 80);">如果你只是想要</font>**<font style="color:rgb(44, 62, 80);">使用这些符号，你必须要使用实体的形式</font>**<font style="color:rgb(44, 62, 80);">，像是 </font>`<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">&lt;</font>`<font style="color:rgb(44, 62, 80);"> 和 </font>`<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">&amp;</font>`<font style="color:rgb(44, 62, 80);">。</font>

##### <font style="color:rgb(35, 35, 38);">必须掌握的核心转义(补)【html中】</font>
| **原始字符** | **转义后的样子** | **说明** |
| :--- | :--- | :--- |
| `<` | `&lt;` | 小于号，因为会被误认为HTML标签开头，必须转义 |
| `>` | `&gt;` | 大于号，因为会被误认为HTML标签结尾，必须转义 |
| `&` | `&amp;` | 和号，因为它本身是转义的起始符，必须转义 |
| `"` | `&quot;` | 双引号，在HTML标签属性里使用时需要转义 |
| `'` | `&apos;` | 单引号，HTML5标准支持 |


##### 故而，例子
###### 在html中（手动）
<font style="color:rgb(44, 62, 80);">如果你要打「AT&T」 ，你必须要写成「</font>`<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">AT</font><font style="color:rgb(71, 101, 130);background-color:#FDE6D3;">&amp</font><font style="color:rgb(71, 101, 130);background-color:#E6DCF9;">;</font><font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">T</font>`<font style="color:rgb(44, 62, 80);">」 ，还得转换网址内的 </font>`<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">&</font>`<font style="color:rgb(44, 62, 80);"> 符号，如果你要链接到：</font>

```plain
http://images.google.com/images?num=30&q=larry+bird
```

<font style="color:rgb(44, 62, 80);">你必须要把网址转成：</font>

```plain
http://images.google.com/images?num=30&amp;q=larry+bird
```

<font style="color:rgb(44, 62, 80);">才能放到链接标签的 </font>`<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">href</font>`<font style="color:rgb(44, 62, 80);"> 属性里。</font>

###### <font style="color:rgb(44, 62, 80);">markdown（自动）</font>
<font style="color:rgb(44, 62, 80);">Markdown 允许你直接使用这些符号，它帮你自动转义字符。</font>

<font style="color:rgb(44, 62, 80);">如果你使用 </font>`<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">&</font>`<font style="color:rgb(44, 62, 80);"> 符号的作为 HTML 实体的一部分，那么它不会被转换，而在其它情况下，它则会被转换成 </font>`<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">&amp;</font>`<font style="color:rgb(44, 62, 80);">。</font>

```plain
&copy;
```

<font style="color:rgb(44, 62, 80);">Markdown 将不会对这段文字做修改，但是如果你这样写：</font>

```plain
AT&T
```

<font style="color:rgb(44, 62, 80);">Markdown 就会将它转为：</font>

```plain
AT&amp;T
```

<font style="color:rgb(44, 62, 80);">类似的状况也会发生在</font><font style="color:rgb(44, 62, 80);"> </font>`<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);"><</font>`<font style="color:rgb(44, 62, 80);"> </font><font style="color:rgb(44, 62, 80);">符号上，因为 Markdown 支持</font><font style="color:rgb(44, 62, 80);"> </font>[<font style="color:rgb(62, 175, 124);">行内 HTML</font>](https://markdown.com.cn/basic-syntax/#%E5%86%85%E8%81%94-html)<font style="color:rgb(44, 62, 80);"> </font><font style="color:rgb(44, 62, 80);">，如果你使用</font><font style="color:rgb(44, 62, 80);"> </font>`<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);"><</font>`<font style="color:rgb(44, 62, 80);"> </font><font style="color:rgb(44, 62, 80);">符号作为 HTML 标签的分隔符，那 Markdown 也不会对它做任何转换，但是如果你是写：</font>

```plain
4 < 5
```

<font style="color:rgb(44, 62, 80);">Markdown 将会把它转换为：</font>

```plain
4 &lt; 5
```

### <font style="color:rgb(44, 62, 80);">内嵌 HTML 标签</font>
<font style="color:rgb(44, 62, 80);">对于 Markdown 涵盖范围之外的标签，都可以直接在文件里面用 HTML 本身。如需使用 HTML，不需要额外标注这是 HTML 或是 Markdown，</font><font style="color:rgb(44, 62, 80);background-color:#E6DCF9;">只需 HTML 标签添加到 Markdown 文本中即可</font><font style="color:rgb(44, 62, 80);">。</font>

#### <font style="color:rgb(44, 62, 80);">行级內联标签</font>
<font style="color:rgb(44, 62, 80);">HTML 的行级內联标签如 </font>`<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);"><span></font>`<font style="color:rgb(44, 62, 80);">、</font>`<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);"><cite></font>`<font style="color:rgb(44, 62, 80);">、</font>`<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);"><del></font>`<font style="color:rgb(44, 62, 80);"> </font><font style="color:rgb(44, 62, 80);background-color:#E6DCF9;">不受限制</font><font style="color:rgb(44, 62, 80);">，可以在 Markdown 的段落、列表或是标题里任意使用。</font>

```plain
This **word** is bold. This <em>word</em> is italic.
```

<font style="color:rgb(44, 62, 80);">渲染效果如下:</font>

<font style="color:rgb(44, 62, 80);">This </font>**<font style="color:rgb(44, 62, 80);">word</font>**<font style="color:rgb(44, 62, 80);"> is bold. This </font>_<font style="color:rgb(44, 62, 80);">word</font>_<font style="color:rgb(44, 62, 80);"> is italic.</font>

#### <font style="color:rgb(44, 62, 80);">区块标签</font>
<font style="color:rgb(44, 62, 80);">区块元素──比如 </font>`<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);"><div></font>`<font style="color:rgb(44, 62, 80);">、</font>`<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);"><table></font>`<font style="color:rgb(44, 62, 80);">、</font>`<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);"><pre></font>`<font style="color:rgb(44, 62, 80);">、</font>`<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);"><p></font>`<font style="color:rgb(44, 62, 80);"> 等标签，必须在</font><font style="color:rgb(44, 62, 80);background-color:#E6DCF9;">前后加上空行</font><font style="color:rgb(44, 62, 80);">，以便于内容区分。</font>

<font style="color:rgb(44, 62, 80);">而且这些元素的开始与结尾标签，不可以用 tab 或是空白来缩进。</font>

<font style="color:rgb(44, 62, 80);">Markdown 会自动识别这区块元素，避免在区块标签前后加上没有必要的 </font>`<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);"><p></font>`<font style="color:rgb(44, 62, 80);"> 标签。</font>

<font style="color:rgb(44, 62, 80);">例如，在 Markdown 文件里加上一段 HTML 表格：</font>

```plain
This is a regular paragraph.

<table>
    <tr>
        <td>Foo</td>
    </tr>
</table>

This is another regular paragraph.
```

<font style="color:rgb(44, 62, 80);">请注意，Markdown 语法在 </font><font style="color:rgb(44, 62, 80);background-color:#E6DCF9;">HTML 区块标签中将不会被进行处理</font><font style="color:rgb(44, 62, 80);">。例如，你无法在 HTML 区块内使用 Markdown 形式的</font>`<font style="color:rgb(71, 101, 130);background-color:rgba(27, 31, 35, 0.05);">*强调*</font>`<font style="color:rgb(44, 62, 80);">。</font><font style="color:rgb(44, 62, 80);background-color:#E6DCF9;">【应该就是不能混合使用】</font>



### 总结（快速可直接看【个人理】）
![画板](https://cdn.nlark.com/yuque/0/2026/jpeg/61947449/1776534909905-4dfc5e72-ea9d-42d4-a001-eb598ef4fa33.jpeg)

## linux 系统知识了解
### 系统
linux 系统可以选择装 Kali 或 Ubuntu，【这两个都搞了】

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/61947449/1776535165276-0f307063-b991-4538-848e-e8761f7e48b1.png)

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/61947449/1776535260499-409a9745-649d-4c33-8d48-e5a873b146a7.png)

但是个人对虚拟机使用的频率还是不高

#### 知识点的学习
[Linux 教程 | 菜鸟教程](https://www.runoob.com/linux/linux-tutorial.html)

[史上最全的Linux常用命令汇总（超全面！超详细！）收藏这一篇就够了！-CSDN博客](https://blog.csdn.net/weixin_44895651/article/details/105289038?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522972f9b1a663c2d6aefefccf5ddd72592%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=972f9b1a663c2d6aefefccf5ddd72592&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_positive~default-1-105289038-null-null.142%5Ev102%5Epc_search_result_base8&utm_term=linux%E5%B8%B8%E7%94%A8%E5%91%BD%E4%BB%A4%E5%A4%A7%E5%85%A8&spm=1018.2226.3001.4187)

[Linux入门教程（非常详细）从零基础入门到精通，看完这一篇就够了_linux学习-CSDN博客](https://blog.csdn.net/bigbangbangbang1/article/details/131575669)

##### 云服务器
[https://www.runoob.com/linux/linux-cloud-server.html](https://www.runoob.com/linux/linux-cloud-server.html)

要使用云服务器的时候看这个贴子

##### Linux命令
<font style="background-color:#FBDE28;">【我很好奇这个命令是要都背下来吗。。。】</font>

+ [Linux 命令大全 | 菜鸟教程](https://www.runoob.com/linux/linux-command-manual.html)【总结板块】
+ [Linux 教程 | 菜鸟教程](https://www.runoob.com/linux/linux-tutorial.html)
+ [史上最全的Linux常用命令汇总（超全面！超详细！）收藏这一篇就够了！-CSDN博客](https://blog.csdn.net/weixin_44895651/article/details/105289038?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522972f9b1a663c2d6aefefccf5ddd72592%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=972f9b1a663c2d6aefefccf5ddd72592&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_positive~default-1-105289038-null-null.142%5Ev102%5Epc_search_result_base8&utm_term=linux%E5%B8%B8%E7%94%A8%E5%91%BD%E4%BB%A4%E5%A4%A7%E5%85%A8&spm=1018.2226.3001.4187)
+ [Linux入门教程（非常详细）从零基础入门到精通，看完这一篇就够了_linux学习-CSDN博客](https://blog.csdn.net/bigbangbangbang1/article/details/131575669)
+ 这四个都是关于命令的

##### 基础知识
###### 什么是Linux
`<font style="color:#DF2A3F;">Linux</font>`:<font style="color:rgb(35, 35, 38);">它是一个开源免费、稳定高效、适合多用户使用的操作系统，从个人学习到企业级服务器都能用到，也是做网络安全渗透测试的常用系统</font>

###### 什么是shell?
<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/jpeg/61947449/1776536080344-d6110c5c-fedd-4fef-8556-89c0825399a3.jpeg)

这个黑色面板就是shell

1. Shell是一个程序，提供一个**与用户对话的环境**。这个环境只有一个**命令提示符**，让用户从键盘输入命令，所以又称为**命令行环境**（command line interface，简写为CLI）。Shell 接收到用户输入的命令，将命令送入操作系统执行，并将结果返回给用户。
2. Shell是一个**命令解释器，解释用户输入的命令**。它支持变量、条件判断、循环操作等语法，所以用户可以用Shell命令写出各种小程序，又称为Shell脚本。这些脚本都通过Shell的解释执行，而不通过编译。
3. Shell是一个**工具箱**，提供了各种小工具，供用户方便地使用操作系统的功能。

###### <font style="color:rgb(77, 77, 77);">Shell 的种类</font>
【目前个人见过的，bash算一个】

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/61947449/1776536319532-ac15a2ed-b398-43da-8ad1-1dbd93de868a.png)

<font style="color:rgb(85, 86, 102);">通过执行</font>`<font style="color:rgb(199, 37, 78);">echo $SHELL</font>`<font style="color:rgb(85, 86, 102);">命令可以查看到当前正在使用的</font>`<font style="color:rgb(199, 37, 78);">Shell</font>`<font style="color:rgb(85, 86, 102);">。还可以通过</font>`<font style="color:rgb(199, 37, 78);">cat /etc/shells</font>`<font style="color:rgb(85, 86, 102);">查看当前系统安装的所有</font>`<font style="color:rgb(199, 37, 78);">Shell</font>`<font style="color:rgb(85, 86, 102);">种类。</font>

###### <font style="color:rgb(85, 86, 102);">命令</font>
<font style="color:rgb(77, 77, 77);">执行一个简单的命令</font>`<font style="color:rgb(199, 37, 78);background-color:rgb(249, 242, 244);">pwd</font>`<font style="color:rgb(77, 77, 77);">：</font>

```plain
[root@iZm5e8dsxce9ufaic7hi3uZ ~]# pwd  
/root
【查当前所在目录的】
```

<font style="color:rgb(85, 86, 102);">命令解析：</font>

+ <font style="color:rgb(85, 86, 102);">root：表示用户名；</font>
+ <font style="color:rgb(85, 86, 102);">iZm5e8dsxce9ufaic7hi3uZ：表示</font><font style="color:rgb(85, 86, 102);background-color:#CEF5F7;">主机名</font><font style="color:rgb(85, 86, 102);">；</font>
+ <font style="color:rgb(85, 86, 102);">~：表示目前所在目录为家目录，其中root用户的家目录是 /root普通用户的家目录在 /home 下；</font>
+ <font style="color:rgb(85, 86, 102);">#：指示你所具有的权限（</font><font style="color:rgb(85, 86, 102);background-color:#CEF5F7;">root用户为# ，普通用户为$ </font><font style="color:rgb(85, 86, 102);">）。</font>
+ <font style="color:rgb(85, 86, 102);">执行</font>`<font style="color:rgb(85, 86, 102);">whoami</font>`<font style="color:rgb(85, 86, 102);">命令可以查看当前</font>**<font style="color:rgb(85, 86, 102);">用户名</font>**<font style="color:rgb(85, 86, 102);">；</font>
+ <font style="color:rgb(85, 86, 102);">执行</font>`<font style="color:rgb(85, 86, 102);">hostname</font>`<font style="color:rgb(85, 86, 102);">命令可以查看当前</font>**<font style="color:rgb(85, 86, 102);">主机名</font>**<font style="color:rgb(85, 86, 102);">；</font>

<font style="color:rgb(85, 86, 102);">命令格式</font>

`<font style="color:rgb(85, 86, 102);">command parameters（命令 参数）  </font>`

<font style="color:rgb(85, 86, 102);">长短参数</font>

```php
单个参数：ls -a（a 是英文 all 的缩写，表示“全部”）  
多个参数：ls -al（全部文件 + 列表形式展示）  
单个长参数：ls --all  
多个长参数：ls --reverse --all  
长短混合参数：ls --all -l  
```

<font style="color:rgb(85, 86, 102);">参数值</font>

```php
短参数：command -p 10（例如：ssh root@121.42.11.34 -p 22）  
长参数：command --paramters=10（例如：ssh root@121.42.11.34 --port=22）  

```

###### 快捷方式
【这个复制粘贴和windows里的ctrl +c不一样】

```php
通过上下方向键 ↑ ↓ 来调取过往执行过的Linux命令；

命令或参数仅需输入前几位就可以用 Tab 键补全；

Ctrl + R ：用于查找使用过的命令（history命令用于列出之前使用过的所有命令，然后输入!命令加上编号 (!2) 就可以直接执行该历史命令）；

Ctrl + L：清除屏幕并将当前行移到页面顶部；

Ctrl + C：中止当前正在执行的命令；

Ctrl + U：从光标位置剪切到行首；

Ctrl + K：从光标位置剪切到行尾；

Ctrl + W：剪切光标左侧的一个单词；

Ctrl + Y：粘贴Ctrl + U | K | Y剪切的命令；

Ctrl + A：光标跳到命令行的开头；

Ctrl + E：光标跳到命令行的结尾；

Ctrl + D：关闭Shell会话；

```

###### 文件和目录
<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/jpeg/61947449/1776585698228-085b6b1b-bd55-4c52-8d6b-4407403c7331.jpeg)

查询路径【pwd/which】

