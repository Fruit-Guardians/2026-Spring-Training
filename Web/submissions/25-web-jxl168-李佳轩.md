## 工具安装
firefox浏览器

<img src="https://cdn.nlark.com/yuque/0/2026/png/67413918/1775983703972-1e5102e3-95c3-4bd4-ad63-7d51d5a189ca.png" width="207" title="" crop="0,0,1,1" id="oC2Mh" class="ne-image"><img src="https://cdn.nlark.com/yuque/0/2026/png/67413918/1775983712695-1d3eb363-eedb-43fb-86df-8f6f572a56a4.png" width="84" title="" crop="0,0,1,1" id="u2ad366e1" class="ne-image">

hackbar

<img src="https://cdn.nlark.com/yuque/0/2026/png/67413918/1775981657273-0938fbcd-1e2f-46f0-a4b5-165c761d32d6.png" width="435" title="" crop="0,0,1,1" id="u9f2db19f" class="ne-image">

yakit

<img src="https://cdn.nlark.com/yuque/0/2026/png/67413918/1775999897171-ca8c325c-e0a2-4116-b18b-ed442aef230a.png" width="431" title="" crop="0,0,1,1" id="u736895c0" class="ne-image">

dirsearch

先安装python，再输入指令下载<font style="color:rgb(31, 35, 40);">dirsearch</font>

<img src="https://cdn.nlark.com/yuque/0/2026/png/67413918/1776056464373-76362b90-e7d1-4b9e-bf8e-c574b694c996.png" width="448" title="" crop="0,0,1,1" id="u539343f6" class="ne-image">

AI

网页版的deepseek

## write up
+ [<font style="color:rgb(9, 105, 218);">[SWPUCTF 2021 新生赛]gift_F12</font>](https://www.nssctf.cn/problem/382)<font style="color:rgb(31, 35, 40);"> </font>

<font style="color:rgb(51, 51, 51);">开启环境之后，在新标签页中打开链接，F12查看源代码，Ctrl+F找到隐藏在网站源码中的flag。</font>

<img src="https://cdn.nlark.com/yuque/0/2026/png/67413918/1776262205763-6df109b4-e159-4941-b03c-30630589bcfc.png" width="650" title="" crop="0,0,1,1" id="u831909ec" class="ne-image">

+ [<font style="color:rgb(9, 105, 218);">[qsnctf-NO.0902]robots.txt</font>](https://www.qsnctf.com/#/main/driving-range?page=1&category=&difficulty=&keyword=robots.txt)

<font style="color:rgb(51, 51, 51);">访问https://域名+端口/robots.txt 得到3个文件名，再访问secret.php，得到账号密码登录即可找到flag</font>

<img src="https://cdn.nlark.com/yuque/0/2026/png/67413918/1776312911102-7ff1ba17-ce1d-4035-a371-f443e694c866.png" width="659.3333740234375" title="" crop="0,0,1,1" id="u0a6f766e" class="ne-image">

## Linux基础学习
### 什么是Linux
<font style="color:rgb(77, 77, 77);">Linux 是一套开放源代码程序的、可以自由传播的类 Unix 操作系统软件。</font>

### <font style="color:rgb(77, 77, 77);">Linux基本指令</font>
#####  ls指令
<font style="color:rgb(77, 77, 77);">对于目录，该命令列出该目录下的所有子目录与文件。对于文件，将列出文件名以及其他信息。</font>

**<font style="color:rgb(85, 86, 102);background-color:rgb(238, 240, 244);">常用功能</font>**<font style="color:rgb(85, 86, 102);background-color:rgb(238, 240, 244);">：</font>

**<font style="color:rgb(85, 86, 102);background-color:rgb(238, 240, 244);">-l:</font>**<font style="color:rgb(85, 86, 102);background-color:rgb(238, 240, 244);"> 列出文件的详细信息。</font><font style="color:rgb(77, 77, 77);">  
</font><font style="color:rgb(85, 86, 102);background-color:rgb(238, 240, 244);">-</font>**<font style="color:rgb(85, 86, 102);background-color:rgb(238, 240, 244);">a:</font>**<font style="color:rgb(85, 86, 102);background-color:rgb(238, 240, 244);"> 列出目录下的所有文件，包括以 . 开头的隐含文件</font><font style="color:rgb(77, 77, 77);">  
</font>**<font style="color:rgb(85, 86, 102);background-color:rgb(238, 240, 244);">-d:</font>**<font style="color:rgb(85, 86, 102);background-color:rgb(238, 240, 244);"> 将目录象文件一样显示，而不是显示其下的文件。 如：ls –d 指定目录</font>

##### pwd指令
<font style="color:rgb(77, 77, 77);">显示用户当前所在的目录</font>

#####  cd 指令
<font style="color:rgb(77, 77, 77);">改变工作目录。将当前工作目录改变到指定的目录下。</font>

**<font style="color:rgb(85, 86, 102);background-color:rgb(238, 240, 244);">常用功能</font>**<font style="color:rgb(85, 86, 102);background-color:rgb(238, 240, 244);">：</font>

<font style="color:rgb(85, 86, 102);background-color:rgb(238, 240, 244);">-.：保持再当前目录不变</font>

<font style="color:rgb(85, 86, 102);background-color:rgb(238, 240, 244);">-...：切换到上级目录</font>

<font style="color:rgb(85, 86, 102);background-color:rgb(238, 240, 244);">--：可以在最近两次目录之间来回切换</font>

##### touch指令
<font style="color:rgb(77, 77, 77);">touch命令参数可更改文档或目录的日期时间，包括存取时间和更改时间，或者新建一个不存在的文件。（touch指令创造的是一个文件！）</font>

##### mkdir指令
<font style="color:rgb(77, 77, 77);">在当前目录下创建一个名为 “dirname”的目录（mkdir创建的是目录！）</font>  
**<font style="color:rgb(85, 86, 102);background-color:rgb(238, 240, 244);">常用选项：</font>**

<font style="color:rgb(85, 86, 102);background-color:rgb(238, 240, 244);">-p：此时若路径中的某些目录尚不存在,加上此选项后,系统将自动建立</font>  
<font style="color:rgb(85, 86, 102);background-color:rgb(238, 240, 244);">好那些尚不存在的目录(</font>**<font style="color:rgb(85, 86, 102);background-color:rgb(238, 240, 244);">递归创建多级目录</font>**<font style="color:rgb(85, 86, 102);background-color:rgb(238, 240, 244);">)</font>

##### rmdir指令&&rm指令
rmdir指令

<font style="color:rgb(77, 77, 77);">删除空目录</font>

**<font style="color:rgb(85, 86, 102);background-color:rgb(238, 240, 244);">常用选项</font>**

<font style="color:rgb(85, 86, 102);background-color:rgb(238, 240, 244);">*p 当子目录被删除后如果父目录也变成空目录的话，就连带父目录一起删除</font>

<font style="color:rgb(85, 86, 102);background-color:rgb(238, 240, 244);"></font>

<font style="color:rgb(77, 77, 77);">rm指令</font>

<font style="color:rgb(77, 77, 77);">删除文件或目录（删除目录时，要加上-r选项）文件删除后不能恢复。</font>

**<font style="color:rgb(85, 86, 102);background-color:rgb(238, 240, 244);">常用选项：</font>**

<font style="color:rgb(85, 86, 102);background-color:rgb(238, 240, 244);">-f 即使文件属性为只读(即写保护)，亦直接删除  
</font><font style="color:rgb(85, 86, 102);background-color:rgb(238, 240, 244);">-i 删除前逐一询问确认 (这个一般用于普通用户，因为root用户，在你删除文件时，默认会询问的)  
</font><font style="color:rgb(85, 86, 102);background-color:rgb(238, 240, 244);">-r 删除目录及其下所有文件</font>

##### man指令
<font style="color:rgb(77, 77, 77);">访问Linux手册页的命令</font>

**<font style="color:rgb(85, 86, 102);background-color:rgb(238, 240, 244);">常用选项</font>**<font style="color:rgb(85, 86, 102);background-color:rgb(238, 240, 244);">：</font>

<font style="color:rgb(85, 86, 102);background-color:rgb(238, 240, 244);">-k 根据关键字搜索联机帮助</font>

<font style="color:rgb(85, 86, 102);background-color:rgb(238, 240, 244);">空格：显示首页下一屏</font>

<font style="color:rgb(85, 86, 102);background-color:rgb(238, 240, 244);">enter键：一次滚动手册页的一行  
</font><font style="color:rgb(85, 86, 102);background-color:rgb(238, 240, 244);">num 只在第num章节找  
</font><font style="color:rgb(85, 86, 102);background-color:rgb(238, 240, 244);">-a 将所有章节的都显示出来，比如 man printf 它缺省从第一章开始搜索，知道就停止，用a选项，当按 下q退出，他会继续往后面搜索，直到所有章节都搜索完毕</font>

##### cp指令
<font style="color:rgb(77, 77, 77);">复制文件或目录</font>

**<font style="color:rgb(85, 86, 102);background-color:rgb(238, 240, 244);">常用选项：</font>**

<font style="color:rgb(85, 86, 102);background-color:rgb(238, 240, 244);">-f 或 --force 强行复制文件或目录， 不论目的文件或目录是否已经存在</font>

<font style="color:rgb(85, 86, 102);background-color:rgb(238, 240, 244);">-i 或 --interactive 覆盖文件之前先询问用户</font>

<font style="color:rgb(85, 86, 102);background-color:rgb(238, 240, 244);">-r递归处理，将指定目录下的文件与子目录一并处理。若源文件或目录的形态，不属于目录或符号链 接，则一律视为普通文件处理</font>

<font style="color:rgb(85, 86, 102);background-color:rgb(238, 240, 244);">-R 或 --recursive递归处理，将指定目录下的文件及子目录一并处理</font>

##### mv指令
视mv命令中第二个参数类型的不同（是目标文件还是目标目录），mv命令将文件重命名或将其移至一个新的 目录中。

当第二个参数类型是文件时，mv命令完成文件重命名，此时，源文件只能有一个（也可以是源目录名），它 将所给的源文件或目录重命名为给定的目标文件名。

当第二个参数是已存在的目录名称时，源文件或目录参数可以有多个，mv命令将各参数指定的源文件均移至 目标目录中。

**<font style="color:rgb(85, 86, 102);background-color:rgb(238, 240, 244);">常用选项</font>**<font style="color:rgb(85, 86, 102);background-color:rgb(238, 240, 244);">：</font>

<font style="color:rgb(85, 86, 102);background-color:rgb(238, 240, 244);">-f ：force 强制的意思，如果目标文件已经存在，不会询问而直接覆盖</font>

<font style="color:rgb(85, 86, 102);background-color:rgb(238, 240, 244);">-i ：若目标文件 (destination) 已经存在时，就会询问</font>

##### echo指令
将字符串输入到屏幕上。  
通常在使用它时，配合着 ’ > '(输出重定向使用)

##### cat指令
查看目标文件的内容（当文件中储存的数据较少时使用）  
**<font style="color:rgb(85, 86, 102);background-color:rgb(238, 240, 244);">常用选项</font>**<font style="color:rgb(85, 86, 102);background-color:rgb(238, 240, 244);">：</font>  
**<font style="color:rgb(85, 86, 102);background-color:rgb(238, 240, 244);">-b</font>**<font style="color:rgb(85, 86, 102);background-color:rgb(238, 240, 244);"> 对非空输出行编号</font>  
**<font style="color:rgb(85, 86, 102);background-color:rgb(238, 240, 244);">-n</font>**<font style="color:rgb(85, 86, 102);background-color:rgb(238, 240, 244);"> 对输出的所有行编号</font>  
**<font style="color:rgb(85, 86, 102);background-color:rgb(238, 240, 244);">-s</font>**<font style="color:rgb(85, 86, 102);background-color:rgb(238, 240, 244);"> 不输出多行空行</font>

##### more指令
more命令，功能类似 cat （当文件储存数据较大时使用）（按回车（Enter）时，会向下显示数据，但只能向下显示，无法查看之前的数据）

**<font style="color:rgb(85, 86, 102);background-color:rgb(238, 240, 244);">常用选项</font>**<font style="color:rgb(85, 86, 102);background-color:rgb(238, 240, 244);">：  
</font><font style="color:rgb(85, 86, 102);background-color:rgb(238, 240, 244);">-n 对输出的所有行编号  
</font><font style="color:rgb(85, 86, 102);background-color:rgb(238, 240, 244);">q 退出more</font>

##### less指令
less与more类似，但使用less可以随意浏览文件，而more仅能向前移动，却不能向后移动，而且less在查看之前 不会加载整个文件。

**<font style="color:rgb(85, 86, 102);background-color:rgb(238, 240, 244);">常用选项：</font>**

<font style="color:rgb(85, 86, 102);background-color:rgb(238, 240, 244);">-i 忽略搜索时的大小写</font>

<font style="color:rgb(85, 86, 102);background-color:rgb(238, 240, 244);">-N 显示每行的行号</font>

<font style="color:rgb(85, 86, 102);background-color:rgb(238, 240, 244);">/字符串：向下搜索“字符串”的功能</font>

<font style="color:rgb(85, 86, 102);background-color:rgb(238, 240, 244);">?字符串：向上搜索“字符串”的功能</font>

<font style="color:rgb(85, 86, 102);background-color:rgb(238, 240, 244);">n：重复前一个搜索（与 / 或 ? 有关）</font>

<font style="color:rgb(85, 86, 102);background-color:rgb(238, 240, 244);">N：反向重复前一个搜索（与 / 或 ? 有关）</font>

<font style="color:rgb(85, 86, 102);background-color:rgb(238, 240, 244);">q:quit</font>

##### head指令
用来显示档案的开头至标准输出中，默认head命令打印其相应文件的开头10行。

**<font style="color:rgb(85, 86, 102);background-color:rgb(238, 240, 244);">常用选项</font>**<font style="color:rgb(85, 86, 102);background-color:rgb(238, 240, 244);">：  
</font><font style="color:rgb(85, 86, 102);background-color:rgb(238, 240, 244);">-n<行数> 显示的行数</font>

##### tail指令
用于显示指定文件末尾内容，不指定文件时，作为输入信息进行处理。常用查看日志文件。

**<font style="color:rgb(85, 86, 102);background-color:rgb(238, 240, 244);">常用选项</font>**<font style="color:rgb(85, 86, 102);background-color:rgb(238, 240, 244);">:  
</font><font style="color:rgb(85, 86, 102);background-color:rgb(238, 240, 244);">-f 循环读取  
</font><font style="color:rgb(85, 86, 102);background-color:rgb(238, 240, 244);">-n<行数> 显示行数</font>

##### date指令
+ 在显示方面，使用者可以设定欲显示的格式，格式设定为一个加号后接数个标记，其中常用的标记列表如下

%H : 小时(00…23)

%M : 分钟(00…59)

%S : 秒(00…61)

%X : 相当于 %H:%M:%S %d : 日 (01…31)

%m :月份 (01…12)

%Y : 完整年份 (0000…9999)

%F : 相当于 %Y-%m-%d



+ 在设定时间方面

date -s //设置当前时间，只有root权限才能设置，其他只能查看。

date -s 20080523 //设置成20080523，这样会把具体时间设置成空00:00:00

date -s 01:01:01 //设置具体时间，不会对日期做更改

date -s “01:01:01 2008-05-23″ //这样可以设置全部时间

date -s “01:01:01 20080523″//这样可以设置全部时间

date -s “2008-05-23 01:01:01″ //这样可以设置全部时间

date -s “20080523 01:01:01″ //这样可以设置全部时间



+ 时间戳

时间->时间戳：date +%s

时间戳->时间：date -d@1508749502 Unix时间戳（英文为Unix epoch, Unix time, POSIX time 或 Unix timestamp）是从1970年1月1（UTC/GMT的午夜）开始所经过的秒数，不考虑闰秒



##### find指令
用于在文件树种查找文件，并作出相应的处理（可能访问磁盘）

**<font style="color:rgb(85, 86, 102);background-color:rgb(238, 240, 244);">常用选项</font>**<font style="color:rgb(85, 86, 102);background-color:rgb(238, 240, 244);">：  
</font><font style="color:rgb(85, 86, 102);background-color:rgb(238, 240, 244);">-name 按照文件名查找文件。  
</font><font style="color:rgb(85, 86, 102);background-color:rgb(238, 240, 244);">name左边的目录是查找目录，右边是查找文件或目录</font>

##### grep指令
在文件中搜索字符串，将找到的行打印出来（在默认情况下，是区分大小写的。当搜索为空时，会把所有内容显示出来）

**<font style="color:rgb(85, 86, 102);background-color:rgb(238, 240, 244);">常用选项</font>**<font style="color:rgb(85, 86, 102);background-color:rgb(238, 240, 244);">：</font>

<font style="color:rgb(85, 86, 102);background-color:rgb(238, 240, 244);">-i ：忽略大小写的不同，所以大小写视为相同  
</font><font style="color:rgb(85, 86, 102);background-color:rgb(238, 240, 244);">-n ：顺便输出行号  
</font><font style="color:rgb(85, 86, 102);background-color:rgb(238, 240, 244);">-v ：反向选择，亦即显示出没有 ‘搜寻字符串’ 内容的那</font>

##### which指令
<font style="color:rgba(0, 0, 0, 0.75);">which 命令可以查看执行命令所在位置</font>

<font style="color:rgb(85, 86, 102);background-color:rgb(238, 240, 244);">/etc/passwd 是用于保存用户信息的文件</font>

<font style="color:rgb(85, 86, 102);background-color:rgb(238, 240, 244);">/usr/bin/passwd 是用于修改用户密码的程序</font>

<font style="color:rgb(85, 86, 102);background-color:rgb(238, 240, 244);"></font>

##### 组管理（通过sudo执行）
| **<font style="color:rgb(79, 79, 79);">命令</font>** | **<font style="color:rgb(79, 79, 79);">作用</font>** |
| :---: | :---: |
| <font style="color:rgb(79, 79, 79);">groupadd 组名</font> | <font style="color:rgb(79, 79, 79);">添加组</font> |
| <font style="color:rgb(79, 79, 79);">groupdel 组名</font> | <font style="color:rgb(79, 79, 79);">删除组</font> |
| <font style="color:rgb(79, 79, 79);">cat /etc/group</font> | <font style="color:rgb(79, 79, 79);">确认组信息</font> |
| <font style="color:rgb(79, 79, 79);">chgrp -R 组名 文件/目录名</font> | <font style="color:rgb(79, 79, 79);">递归修改文件/目录的所属组</font> |


##### 用户管理<font style="color:rgb(85, 86, 102);background-color:rgb(238, 240, 244);">  
</font>
| 命令 | 作用 | 说明 |
| :---: | :---: | :---: |
| useradd-m-g组新建用户名 | 添加新用户 | -m自动建立用户家目录<br/>-g指定用户所在的组，否则会建立一个和同名的组 |
| passward用户名 | 设置用户密码 | 如果是普通用户，直接用passwd可以修改自己的账户密码 |
| userdel-r用户名 | 删除用户 | -r选项会自动删除用户家目录 |
| cat/etc/passd|grep用户名 | 确认用户信息 | 新建用户后，用户信息会保存在etc/passd文件中 |


##### 切换用户
| **<font style="color:rgb(79, 79, 79);">命令</font>** | **<font style="color:rgb(79, 79, 79);">作用</font>** | **<font style="color:rgb(79, 79, 79);">说明</font>** |
| :---: | :---: | :---: |
| <font style="color:rgb(79, 79, 79);">su - 用户名</font> | <font style="color:rgb(79, 79, 79);">切换用户，并且切换目录</font> | <font style="color:rgb(79, 79, 79);">- 可以切换到用户家目录，否则保持位置不变</font> |
| <font style="color:rgb(79, 79, 79);">exit</font> | <font style="color:rgb(79, 79, 79);">退出当前登录账户</font> | |


##### 修改目录权限
| **<font style="color:rgb(79, 79, 79);">命令</font>** | **<font style="color:rgb(79, 79, 79);">作用</font>** |
| :---: | :---: |
| <font style="color:rgb(79, 79, 79);">chown</font> | <font style="color:rgb(79, 79, 79);">修改拥有者</font> |
| <font style="color:rgb(79, 79, 79);">chgrp</font> | <font style="color:rgb(79, 79, 79);">修改组</font> |
| <font style="color:rgb(79, 79, 79);">chmod</font> | <font style="color:rgb(79, 79, 79);">修改权限</font> |


##### 快捷方式
+ 上下方向键 ↑ ↓ ：来调取过往执行过的Linux命令
+ Tab 键补全：命令或参数仅需输入前几位就
+ Ctrl + R ：用于查找使用过的命令（history命令用于列出之前使用过的所有命令，然后输入!命令加上编号 (!2) 就可以直接执行该历史命令）
+ Ctrl + L：清除屏幕并将当前行移到页面顶部
+ Ctrl + C：中止当前正在执行的命令
+ Ctrl + U：从光标位置剪切到行首
+ Ctrl + K：从光标位置剪切到行尾
+ Ctrl + W：剪切光标左侧的一个单词
+ Ctrl + Y：粘贴Ctrl + U | K | Y剪切的命令
+ Ctrl + A：光标跳到命令行的开头
+ Ctrl + E：光标跳到命令行的结尾
+ Ctrl + D：关闭Shell会话
