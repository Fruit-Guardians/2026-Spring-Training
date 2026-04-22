# Writeup：第一周作业
- ID: `20253001134`
- 方向: Web 
- 日期: 2026-04-17
- 平台/来源: SWPUCTF 2021、MoeCTF 2021
- 题目名称: Web入门三道题 + Linux环境搭建）
- 题目链接/附件: [SWPUCTF 2021新生赛]gift_F12(https://www.nssctf.cn/problem/xxx)
[qsctf-NO.0902]robots.txt(https://www.nssctf.cn/problem/xxx)  [MoeCTF 2021]Web安全入门指北—GET(https://www.nssctf.cn/problem/xxx)

## 题目一：[SWPUCTF 2021] gift_F12
### 目标与范围
- 靶机/远程地址: node7.anna.nssctf.cn:26386
- 漏洞类型: 前端源码泄露
- 约束与规则: 仅在授权实验环境内操作，禁止对平台发起非授权请求

### 环境与依赖
- 操作系统: Windows
- 工具与版本: Edge 浏览器（自带F12开发者工具）
- 语言与版本: 无
- 复现实验: 直接访问view-source:node7.anna.nssctf.cn:26386

### 解题过程
1. 信息收集与初步分析：打开题目页面，无明显交互功能，根据题目名称推测考点为F12源码查看。

2. 漏洞定位与可利用性验证：按下`F12`打开开发者工具，切换至`Elements`面板，逐行检查HTML源码。

3. 构造Payload / Exploit步骤：在页面注释或隐藏标签中找到明文Flag，直接复制即可。

4. 拿到Flag的过程：复制源码中泄露的内容，提交完成解题。

  ![gift-F12源码截图](https://github.com/Moomoon11/my-image-bed/raw/main/gift-F12.png)

5. 常见坑与绕过技巧：部分Flag会写在注释里，不要只看页面显示内容。

### 关键代码
```javascript
flag = "WLMCTF(Welcome to WLMCTF This is the 3G Gift)"; // flag is here
```

##题目二：[qsnctf-NO.0902]robots.txt
###目标与范围
- 靶机/远程地址: http://challenge.qsnctf.com:52879/
- 漏洞类型: 前端源码泄露
- 约束与规则: 仅在授权实验环境内操作，禁止对平台发起非授权请求

### 环境与依赖
- 操作系统: Windows
- 工具与版本: Edge 浏览器
- 语言与版本: 无
- 复现实验: 直接访问http://challenge.qsnctf.com:52879/

### 解题过程
1.  信息收集与初步分析：访问题目首页，根据提示或常规思路访问 `/robots.txt` 文件。  
   得到如下内容（示例）：
```
Disallow: /login.php
Disallow: /admin.php
Disallow: /secret.php
```
这暴露了三个本应禁止爬虫访问的路径。

2.  漏洞定位与可利用性验证：- 依次尝试访问上述路径。  
- `/login.php` 是登录页面，需要账号密码。  
- `/admin.php` 可能需权限，先放一边。  
- `/secret.php` 直接访问，页面中明文字样泄露了账号密码：`admin` / `passw0rd!2025`。

3.  构造Payload / Exploit步骤：使用泄露的账号密码访问 `/login.php`：
- 用户名：`admin`
- 密码：`passw0rd!2025`  
提交登录表单。

4. 登录成功后，页面直接显示 flag。

   ![robots.txt截图](https://github.com/Moomoon11/my-image-bed/raw/main/robots.txt)
​    5.常见坑与绕过技巧：
-`robots.txt` 虽然是标准协议，但并不是安全机制，攻击者可以直接访问。  

- 注意区分大小写，路径需要完全匹配。  
- 若密码含特殊字符（如 `!`），确保浏览器或工具正确编码。

### 关键代码
```python
# 使用 Python requests 自动化获取 flag
import requests

base = "http://靶机地址/"

# 1. 读取 robots.txt
robots = requests.get(base + "robots.txt")
print(robots.text)

# 2. 访问 secret.php 获取账号密码
secret = requests.get(base + "secret.php")
# 假设页面直接显示 "admin / passw0rd!2025"
# 实际可能需要正则提取，此处简化

# 3. 登录 login.php
login_url = base + "login.php"
data = {"username": "admin", "password": "passw0rd!2025"}
resp = requests.post(login_url, data=data)
print(resp.text)   # 应包含 flag
```
##题目三：[MoeCTF 2021]Web 安全入门指北—GET
### 目标与范围
- 靶机/远程地址: http://node5.anna.nssctf.cn:23377/
- 漏洞类型: 前端源码泄露
- 约束与规则: 仅在授权实验环境内操作，禁止对平台发起非授权请求

### 环境与依赖
- 操作系统: Windows
- 工具与版本: Edge 浏览器（自带F12开发者工具）
- 语言与版本: 无
- 复现实验: 直接访问http://node5.anna.nssctf.cn:23377/，在URL后添加参数。

### 解题过程
1.  信息收集与初步分析：打开题目页面，直接显示了 PHP 源码。关键逻辑如下：
   ```php
   <?php
   if(isset($_GET['moe']) && $_GET['moe'] == "flag") {
       include 'flag.php';
       echo $flag;
   } else {
       echo "You need to give me the flag!";
   }
   ?>
```

说明后端接收 GET 参数 moe，当值为 "flag" 时会输出真正的 flag。
2.  漏洞定位与可利用性验证：没有过滤或额外限制，只需向服务器发送一个带有 moe=flag 的 GET 请求即可触发条件。
3.  构造Payload / Exploit步骤：在当前 URL 后面拼接 ?moe=flag，例如：
```
   http://靶机地址/?moe=flag
   ```
   也可以使用 curl：
   ```bash
   curl "http://靶机地址/?moe=flag"
   ```
4. 拿到Flag的过程：访问构造好的 URL 后，页面不再显示提示文字，而是直接输出 flag。

  ![GET请求flag截图](https://github.com/Moomoon11/my-image-bed/raw/main/moe-ctf.png)
5. 常见坑与绕过技巧：
  -注意参数名是 moe 而不是 m0e 或大小写变体，需完全匹配。
  -如果使用 POST 或其他方法将无效，本题仅接受 GET 方式。

### 关键代码
```python
# 使用 Python requests 库获取 flag 的示例
import requests

url = "http://靶机地址/"
params = {"moe": "flag"}
resp = requests.get(url, params=params)
print(resp.text)   # 输出包含 flag 的响应
```


##题目四：Linux环境搭建

###目标与范围

- 靶机/远程地址: 本地 Ubuntu 24.04 LTS 环境
- 学习范围: 文件系统导航、文件增删改查、用户与权限管理、常用命令行操作
- 约束与规则: 仅在本地虚拟机内操作，不涉及真实生产环境

###环境与依赖

- 操作系统: Windows 11 + VMware 17 Pro 运行 Ubuntu 24.04 LTS
- 工具与版本: Bash (5.2.15)，Ubuntu 自带基础工具包
- 语言与版本: Shell 脚本 
- 复现实验: 启动 Ubuntu 虚拟机 → 打开终端（Ctrl+Alt+T）→ 直接输入命令验证

###解题过程

1. 信息收集与初步分析：
学习目标：
· 目录与文件操作（pwd, cd, ls, mkdir, rmdir, touch, cp, mv, rm）
· 文件内容查看（cat, less, head, tail）
· 用户与权限管理（adduser, passwd, userdel, chmod, chown）
· 系统帮助（man, --help）

2. 具体命令学习与验证

2.1 目录与文件基本操作

```bash
# 显示当前工作目录
pwd
# 输出示例：/home/your_id

# 列出目录内容（包括隐藏文件，详细模式）
ls -la

# 切换到家目录并创建实验文件夹
cd ~
mkdir linux_notes
cd linux_notes

# 创建空文件
touch file1.txt

# 复制文件
cp file1.txt file2.txt

# 移动/重命名文件
mv file2.txt backup.txt

# 查看当前目录文件
ls
# 输出：backup.txt  file1.txt

# 删除文件
rm file1.txt

# 删除目录（需要目录为空）
cd ..
rmdir linux_notes      # 因为里面还有 backup.txt，会失败
rm -rf linux_notes     # 强制递归删除
```

2.2 文件内容查看

```bash
# 创建示例文件
echo -e "line1\nline2\nline3\nline4\nline5" > sample.txt

# 完整输出
cat sample.txt

# 分页查看（空格翻页，q 退出）
less sample.txt

# 查看前 2 行
head -n 2 sample.txt

# 查看后 3 行
tail -n 3 sample.txt

# 动态追踪文件末尾（常用于日志）
tail -f /var/log/syslog   # 按 Ctrl+C 退出
```

2.3 用户管理（需 sudo 权限）

```bash
# 创建新用户（会自动创建家目录）
sudo adduser testuser

# 设置/修改用户密码
sudo passwd testuser

# 删除用户（连同家目录和邮件池）
sudo userdel -r testuser
```

2.4 权限管理

```bash
# 创建一个测试文件
touch perms.txt

# 查看当前权限（-rw-r--r-- 表示 644）
ls -l perms.txt

# 修改权限：给所有用户添加执行权限
chmod a+x perms.txt
ls -l perms.txt   # 变为 -rwxr-xr-x

# 使用数字方式修改为 600（仅所有者读写）
chmod 600 perms.txt
ls -l perms.txt   # -rw-------

# 修改文件所有者（需要 sudo）
sudo chown testuser perms.txt
```

2.5 获取帮助

```bash
# 查看命令的简易帮助
ls --help

# 查看完整手册（按 q 退出）
man ls
```
