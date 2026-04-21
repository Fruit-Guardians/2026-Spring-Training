# Web方向第一周作业

**姓名**：[杨俊莹]  
**日期**：2026-04-19

---

## 一、工具安装与使用

### 1. 浏览器开发者工具 (F12)

**安装说明**：浏览器自带功能，无需安装。按F12或右键"检查"即可打开。

**功能说明**：
- 查看网页源代码（Elements/Inspector）
- 调试JavaScript（Console）
- 分析网络请求（Network）
- 查看存储数据（Storage/Application）

**截图**：
![浏览器开发者工具](https://cdn.nlark.com/yuque/0/2026/png/67624642/1776591366212-4bb95864-a536-4f56-9fef-2dccb52c9f38.png?x-oss-process=image%2Fformat%2Cwebp)

---

### 2. Hackbar插件

**安装说明**：
1. 打开Firefox浏览器
2. 访问附加组件商店（about:addons）
3. 搜索"Hackbar"并安装
4. 重启浏览器后按F12在开发者工具栏找到Hackbar标签

**功能说明**：
- 编辑URL参数
- 构造POST请求
- 修改User-Agent、Referer等HTTP头
- 编码/解码工具（URL、Base64、MD5等）

**截图**：
![Hackbar插件](https://cdn.nlark.com/yuque/0/2026/png/67624642/1776591366540-c3a2671e-777f-4aa2-8e2e-b3a425f6cf0e.png?x-oss-process=image%2Fformat%2Cwebp)

*图中显示Hackbar插件已成功安装，可以编辑URL、POST数据、User-Agent等*

---

### 3. Burp Suite

**安装说明**：
1. 下载Burp Suite Community Edition（免费版）
2. 安装Java运行环境（JRE）
3. 启动Burp Suite，配置代理监听127.0.0.1:8080
4. 浏览器配置代理指向Burp

**功能说明**：
- 拦截和修改HTTP/HTTPS请求
- 重放请求（Repeater）
- 暴力破解（Intruder）
- 漏洞扫描

**截图**：
![Burp Suite](https://cdn.nlark.com/yuque/0/2026/png/67624642/1776591367315-06c19820-8084-41d0-9006-1c17011fa3e0.png?x-oss-process=image%2Fformat%2Cwebp)

*图中显示Burp Suite已成功拦截HTTP请求，可以查看和修改请求头信息*

---

### 4. dirsearch

**安装说明**：
```bash
# 使用pip安装
pip install dirsearch

# 或使用git克隆
git clone https://github.com/maurosoria/dirsearch.git
cd dirsearch
pip install -r requirements.txt
```

**功能说明**：
- 网站目录扫描
- 发现隐藏文件和目录
- 支持多线程、自定义字典、文件扩展名过滤

**截图**：
![dirsearch安装](https://cdn.nlark.com/yuque/0/2026/png/67624642/1776591366523-5527bd38-896c-43ff-8bbc-435913990c66.png?x-oss-process=image%2Fformat%2Cwebp)

*dirsearch已安装在Python311的site-packages目录下*

### 5. AI
经常使用豆包，kimi等。
---

## 二、题目Writeup

### 题目1：[SWPUCTF 2021 新生赛]gift_F12

**题目链接**：https://nssctf.cn/problem/2144

**题目描述**：找到flag。

**解题工具**：浏览器开发者工具（F12）

**解题过程**：
1. 访问靶机地址 `node7.anna.nssctf.cn:26582`
2. 按F12打开开发者工具，切换到"源代码"或"元素"标签
3. 查看页面源码，搜索flag

**Flag**：`WLLMCTF{We1c0me_t0_WLLMCTF_Th1s_1s_th3_G1ft}`

**截图**：
![gift_F12解题](https://cdn.nlark.com/yuque/0/2026/png/67624642/1776591367485-950c8701-b8a7-4ff7-aab9-1d880b01eee2.png?x-oss-process=image%2Fformat%2Cwebp)

---

### 题目2：[qsnctf-NO.0902]robots.txt

**题目链接**：https://challenge.qsnctf.com:52971

**题目描述**：通过robots.txt文件发现隐藏路径

**解题工具**：浏览器、Burp Suite

**解题过程**：
1. 访问 `challenge.qsnctf.com:52971/robots.txt`，查看爬虫协议文件
2. 发现Disallow了三个路径：
   ```
   User-agent: *
   Disallow: /login.php
   Disallow: /admin.php
   Disallow: /secret.php
   ```
3. 依次访问这三个路径
4. 访问 `/secret.php`，页面显示：
   - "Nothing to see here"
    - username: admin
    - password: passw0rd!2025
5. 访问 `/login.php`，使用获取的凭据登录
6. 登录成功后跳转到 `/admin.php`，显示flag

**Flag**：`flag{9120084bc5504be7b4bc30af78079ae8}`

**截图**：
- robots.txt内容：
![robots.txt](https://cdn.nlark.com/yuque/0/2026/png/67624642/1776591367236-aa0502a0-f9e2-499e-aa25-68a7fa4d4c97.png?x-oss-process=image%2Fformat%2Cwebp)

- secret.php泄露的凭据：
![secret.php](https://cdn.nlark.com/yuque/0/2026/png/67624642/1776591367247-6b8ff0ac-8d0d-4606-9366-556de409a9de.png?x-oss-process=image%2Fformat%2Cwebp)

- admin.php登录后获取flag：
![admin.php](https://cdn.nlark.com/yuque/0/2026/png/67624642/1776591367515-0320b541-09f6-4bfd-8f82-303bbd0169fd.png?x-oss-process=image%2Fformat%2Cwebp)

---

### 题目3：[MoeCTF 2021]Web安全入门指北—GET

**题目链接**：https://nssctf.cn/problem/6

**题目描述**：学习GET请求传参

**解题工具**：浏览器地址栏、Hackbar

**解题过程**：
1. 访问靶机 `node5.anna.nssctf.cn:28094`，页面直接显示PHP源码
2. 构造Payload：在URL后添加 `?moe=flag`
3. 访问 `node5.anna.nssctf.cn:28094/?moe=flag`，页面直接显示flag

**Flag**：`NSSCTF{417afdb3-72c9-4a14-9375-e751bcb2bd90}`

**截图**：
- 源码页面：
![GET题目源码](https://cdn.nlark.com/yuque/0/2026/png/67624642/1776591367518-087620b0-8b79-491b-84ad-3d1ed2388318.png?x-oss-process=image%2Fformat%2Cwebp)

- 传入参数后获取flag：
![GET题目flag](https://cdn.nlark.com/yuque/0/2026/png/67624642/1776591367668-2253012b-6909-4300-bdab-fa83553ee4e8.png?x-oss-process=image%2Fformat%2Cwebp)

---

## 三、Linux环境搭建

### 环境：Kali Linux虚拟机

**搭建方式**：使用VMware Workstation安装Kali Linux

**搭建步骤**：
1. **下载软件**：
   - VMware Workstation Pro/Player（官网下载）
   - Kali Linux ISO镜像（https://www.kali.org/get-kali/）

2. **创建虚拟机**：
   - 打开VMware，选择"创建新的虚拟机"
   - 选择"自定义"配置
   - 安装来源选择下载的Kali ISO文件
   - 客户机操作系统选择：Linux -> Debian 12.x 64位
   - 命名虚拟机，选择存储位置
   - 选择"将虚拟磁盘存储为单个文件"

**截图**：
![Kali Linux](https://cdn.nlark.com/yuque/0/2026/png/67624642/1776591367834-b9840582-8a28-42fc-8b08-9e6f1b944e06.png?x-oss-process=image%2Fformat%2Cwebp)

---

## 四、Linux基础命令学习笔记

### 1. 文件系统导航

| 命令 | 全称 | 功能 | 常用选项 | 示例 |
|------|------|------|----------|------|
| `pwd` | Print Working Directory | 显示当前路径 | 无 | `pwd` |
| `ls` | List | 列出目录内容 | `-l`详细列表<br>`-a`显示隐藏文件<br>`-h`人类可读大小 | `ls -lah` |
| `cd` | Change Directory | 切换目录 | `..`上级目录<br>`~`用户主目录<br>`-`上次目录 | `cd /var/www/html` |
| `tree` | Tree | 树状显示目录 | `-L`指定层级 | `tree -L 2` |

**实战技巧**：
```bash
cd -                    # 快速回到上次目录
ls -la /home/kali/ctf/  # 查看所有文件含隐藏文件
ls -lh /var/log/        # 以人类可读方式显示大小（KB/MB/GB）
```

---

### 2. 文件操作

| 命令 | 功能 | 常用选项 | 示例 |
|------|------|----------|------|
| `touch` | 创建空文件 | 无 | `touch flag.txt` |
| `mkdir` | 创建目录 | `-p`递归创建 | `mkdir -p web/level1/upload` |
| `rm` | 删除文件/目录 | `-r`递归<br>`-f`强制 | `rm -rf /tmp/test/` |
| `cp` | 复制 | `-r`递归目录 | `cp -r web1/ web2/` |
| `mv` | 移动/重命名 | 无 | `mv old.txt new.txt` |
| `cat` | 查看文件内容 | `-n`显示行号 | `cat -n index.php` |
| `head` | 查看开头 | `-n`指定行数 | `head -20 log.txt` |
| `tail` | 查看结尾 | `-n`行数<br>`-f`实时追踪 | `tail -f access.log` |
| `less` | 分页查看 | 无 | `less large_file.txt` |

**CTF实战**：
```bash
cat /var/www/html/flag.php                    # 查看网站源码中的flag
tail -n 100 /var/log/apache2/access.log       # 查看日志最新100行
find . -name "*.php" -exec wc -l {} + | tail -1   # 统计代码行数
```

---

### 3. 文本搜索与处理

| 命令 | 功能 | 常用选项 | 示例 |
|------|------|----------|------|
| `grep` | 文本搜索 | `-i`忽略大小写<br>`-r`递归<br>`-n`显示行号 | `grep -rn "flag{" ./` |
| `find` | 文件查找 | `-name`按名<br>`-type`按类型<br>`-size`按大小 | `find / -name "flag*" 2>/dev/null` |
| `awk` | 文本处理 | 模式匹配 | `awk '{print $1}' access.log` |
| `sed` | 流编辑器 | `-i`直接修改 | `sed -i 's/old/new/g' file.txt` |
| `sort` | 排序 | `-r`逆序<br>`-n`数字排序 | `sort -nr scores.txt` |
| `uniq` | 去重统计 | `-c`统计次数 | `sort file \| uniq -c` |
| `cut` | 截取字段 | `-d`分隔符<br>`-f`字段 | `cut -d':' -f1 /etc/passwd` |

**CTF实战**：
```bash
grep -rn "flag{" /var/www/html/                           # 在整站源码中搜索flag
find / -name "flag*" -type f -readable 2>/dev/null        # 查找所有可读的flag文件
awk '{print $1}' access.log | sort | uniq -c | sort -nr | head -10   # 统计访问最多的IP
grep -rn "eval\|assert\|system\|exec" --include="*.php" ./  # 提取PHP敏感函数
```

---

### 4. 权限与系统管理

| 命令 | 功能 | 常用选项 | 示例 |
|------|------|----------|------|
| `chmod` | 修改权限 | `+x`添加执行<br>`755`rwxr-xr-x<br>`777`全开 | `chmod +x script.sh` |
| `chown` | 修改所有者 | `-R`递归 | `chown root:root file` |
| `sudo` | 超级用户执行 | `-i`切换到root | `sudo su` |
| `ps` | 查看进程 | `aux`所有进程 | `ps aux \| grep apache` |
| `netstat` | 网络连接 | `-tuln`监听端口 | `netstat -tuln` |
| `ss` | 替代netstat | `-tuln` | `ss -tuln` |
| `kill` | 终止进程 | `-9`强制 | `kill -9 1234` |
| `df` | 磁盘空间 | `-h`人类可读 | `df -h` |
| `du` | 目录大小 | `-sh`汇总 | `du -sh /var/log/` |
| `free` | 内存使用 | `-h`人类可读 | `free -h` |

**权限数字表示**：
```
rwx = 421 = 7      rw- = 420 = 6      r-x = 401 = 5      r-- = 400 = 4

755 = rwxr-xr-x （目录默认）
644 = rw-r--r-- （文件默认）
```

**CTF实战**：
```bash
chmod +x ./exploit.py                           # 给脚本添加执行权限
find / -perm -4000 -type f 2>/dev/null          # 查找所有SUID文件（提权线索）
ps aux | grep -E "apache|nginx"                 # 查看Web服务是否运行
netstat -tuln | grep 80                         # 查看80端口占用情况
```

---

### 5. 网络与下载

| 命令 | 功能 | 常用选项 | 示例 |
|------|------|----------|------|
| `ping` | 测试连通 | `-c`次数 | `ping -c 4 8.8.8.8` |
| `curl` | HTTP工具 | `-v`详细<br>`-X`指定方法<br>`-d`POST数据<br>`-H`添加Header | `curl -X POST -d "name=test" http://target/login` |
| `wget` | 下载文件 | `-O`指定输出名<br>`-r`递归下载 | `wget http://target/robots.txt` |
| `nc` | netcat工具 | `-l`监听<br>`-p`端口<br>`-v`详细 | `nc -lvnp 4444` |
| `nmap` | 端口扫描 | `-sV`版本探测<br>`-sC`默认脚本<br>`-p`指定端口 | `nmap -sV -p 80,443 target.com` |
| `ssh` | 远程登录 | `-p`指定端口<br>`-i`指定密钥 | `ssh root@192.168.1.100` |
| `scp` | 安全复制 | `-r`递归<br>`-P`端口 | `scp file.txt root@host:/tmp/` |

**CTF实战**：
```bash
curl http://challenge.qsnctf.com:52971/robots.txt       # 快速获取网页源码
wget http://target.com/download/challenge.zip           # 下载题目附件
nmap -sV -p- 192.168.1.100                             # 扫描靶机所有端口
nc -lvnp 1234                                          # 监听端口接收反弹shell
```

---

### 6. 压缩解压

| 命令 | 功能 | 常用选项 | 示例 |
|------|------|----------|------|
| `tar` | 打包/解包 | `-c`创建<br>`-x`解压<br>`-z`gzip压缩<br>`-v`显示过程<br>`-f`指定文件名 | `tar -czvf backup.tar.gz ./web/` |
| `zip/unzip` | zip压缩/解压 | `-r`递归 | `zip -r web.zip ./web/` |
| `gzip/gunzip` | gzip压缩/解压 | 无 | `gzip file.txt` |

**示例**：
```bash
tar -czvf web_backup.tar.gz /var/www/html/      # 打包Web目录
tar -xzvf source_code.tar.gz                     # 解压tar.gz
unzip challenge.zip -d ./ctf/                    # 解压CTF附件到指定目录
```

---

### 7. 管道与重定向

| 符号 | 功能 | 示例 |
|------|------|------|
| `\|` | 管道：前一个输出作为后一个输入 | `cat file \| grep "flag"` |
| `>` | 重定向输出（覆盖） | `echo "test" > file.txt` |
| `>>` | 重定向输出（追加） | `echo "more" >> file.txt` |
| `2>` | 重定向错误输出 | `find / -name "flag" 2>/dev/null` |
| `&>` | 重定向所有输出 | `command &> output.log` |

**CTF组合技**：
```bash
grep -rn "flag{" /var/www/ 2>/dev/null | head -5                    # 在大量文件中搜索flag
tail -f /var/log/apache2/access.log | grep "admin"                  # 实时监控日志并过滤
awk '{print $1}' access.log | sort -u > unique_ips.txt              # 提取所有IP并去重保存
find . -name "*.php" -mtime -1 -exec ls -lh {} \;                   # 查找最近修改的PHP文件
```

---

### 8. 其他实用命令

| 命令 | 功能 | 示例 |
|------|------|------|
| `history` | 查看命令历史 | `history \| grep "nmap"` |
| `clear` | 清屏 | `clear` 或 `Ctrl+L` |
| `man` | 查看手册 | `man ls` |
| `echo` | 输出文本 | `echo "flag{test}" > flag.txt` |
| `base64` | Base64编解码 | `echo "test" \| base64` / `echo "dGVzdA==" \| base64 -d` |
| `md5sum` | 计算MD5 | `md5sum file.txt` |
| `sha256sum` | 计算SHA256 | `sha256sum file.txt` |
| `xxd` | 十六进制查看 | `xxd file.bin \| head` |
| `strings` | 提取可打印字符串 | `strings binary \| grep "flag"` |

**示例**：
```bash
echo "ZmxhZ3t0ZXN0fQ==" | base64 -d        # 解码Base64编码的flag
xxd unknown_file | head -1                 # 查看二进制文件头判断类型（如PNG文件头89504e47）
strings ./challenge | grep -i "password"   # 从二进制文件提取字符串
```

---

### 9. Vim编辑器基础

**三种模式**：
1. **普通模式**（默认）：浏览、删除、复制、粘贴
2. **插入模式**（按`i`进入）：编辑文本
3. **命令模式**（按`:`进入）：保存、退出、查找替换

**常用命令**：

| 操作 | 命令 |
|------|------|
| 进入编辑 | `i`（光标前） / `a`（光标后） |
| 保存 | `:w` |
| 退出 | `:q` |
| 保存退出 | `:wq` 或 `ZZ` |
| 强制退出（不保存） | `:q!` |
| 查找 | `/keyword`，按`n`下一个，`N`上一个 |
| 替换 | `:%s/old/new/g`（全局替换） |
| 删除行 | `dd` |
| 复制行 | `yy` |
| 粘贴 | `p`（光标后） / `P`（光标前） |
| 撤销 | `u` |
| 跳转到行首 | `0` |
| 跳转到行尾 | `$` |

---

### 10. 实用快捷键

| 快捷键 | 功能 |
|--------|------|
| `Tab` | 自动补全命令/文件名（按两次显示所有候选） |
| `Ctrl+C` | 终止当前命令 |
| `Ctrl+D` | 退出当前终端 |
| `Ctrl+R` | 搜索历史命令（输入关键字查找） |
| `Ctrl+A` | 光标移到行首 |
| `Ctrl+E` | 光标移到行尾 |
| `Ctrl+U` | 删除光标前所有内容 |
| `Ctrl+K` | 删除光标后所有内容 |
| `Ctrl+W` | 删除光标前一个单词 |
| `!!` | 执行上一条命令 |
| `!n` | 执行历史记录第n条命令（n为数字） |

---