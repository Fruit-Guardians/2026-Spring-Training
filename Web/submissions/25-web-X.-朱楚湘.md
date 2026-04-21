# Web 安全工具安装与使用 Writeup

## 一、工具安装与使用记录

### 1. 浏览器开发者工具（F12 / 查看网页源代码）

**说明**：浏览器自带，无需安装。

**使用记录**：
- 在 Firefox / Chrome 中访问目标网页，按 `F12` 打开开发者工具
- 点击 `Inspector` / `Elements` 可查看网页源代码和 DOM 结构
- 点击 `Network` 标签可查看所有网络请求（后续抓包分析常用）
![alt text](file:///c%3A/Users/freya666/Pictures/Screenshots/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%28119%29.png)

---

### 2. Hackbar 插件安装


**安装步骤**：
1. 打开 Firefox，点击右上角菜单 → 扩展和主题
2. 搜索 "Hackbar"
3. 安装 Hackbar 插件（或 Hackbar Quantum 版本）
4. 安装完成后，按 `F9` 或点击工具栏图标打开 Hackbar
![alt text](file:///c%3A/Users/freya666/Pictures/Screenshots/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%28120%29.png)

**使用记录**：
- Hackbar 可在当前页面直接编辑 GET/POST 参数
- 支持 URL 编码、解码、SQL 注入测试等功能
![alt text](file:///c%3A/Users/freya666/Pictures/Screenshots/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%28126%29.png)

---

### 3. Burp Suite 配置与使用（虚拟机 + 物理机代理抓包）

**环境说明**：
- 物理机：Windows 11 + Burp Suite Community Edition v2026.3.2
- 虚拟机：VMware Workstation 17 Player + Ubuntu + Firefox

**截图**：

![alt text](file:///c%3A/Users/freya666/Pictures/Screenshots/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%28129%29.png)

---

### 4. AI 辅助学习

**使用记录**：
![alt text](file:///c%3A/Users/freya666/Pictures/Screenshots/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%28151%29.png)
![alt text](file:///c%3A/Users/freya666/Pictures/Screenshots/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%28153%29.png)

---

### 5. dirsearch 目录扫描工具

**安装步骤**（Ubuntu 虚拟机中执行）：

```bash
git clone https://github.com/maurosoria/dirsearch.git
cd dirsearch
pip3 install -r requirements.txt
```
![alt text](file:///c%3A/Users/freya666/Pictures/Screenshots/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%28146%29.png)
![alt text](file:///c%3A/Users/freya666/Pictures/Screenshots/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%28148%29.png)
![alt text](file:///c%3A/Users/freya666/Pictures/Screenshots/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%28150%29.png)

---

二、题目 Writeup

题目 1：[SWPUCTF 2021 新生赛] gift F12

解题过程：

1. 打开题目网页
2. 按 F12 打开开发者工具
3. 查看 Inspector / Elements 标签页中的 HTML 代码
4. 在注释或隐藏元素中找到 flag
![alt text](file:///c%3A/Users/freya666/Pictures/Screenshots/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%28159%29.png)
![alt text](file:///c%3A/Users/freya666/Pictures/Screenshots/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%28158%29.png)
![alt text](file:///c%3A/Users/freya666/Pictures/Screenshots/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%28160%29.png)



---

题目 2：[qsnctf-NO.0902] robots.txt

解题过程：

1. 访问 http://<靶机地址>/robots.txt
2. 查看 robots.txt 文件中 Disallow 的路径
3. 访问 Disallow 中隐藏的路径，获取 flag
![alt text](file:///c%3A/Users/freya666/Pictures/Screenshots/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%28166%29.png)
![alt text](file:///c%3A/Users/freya666/Pictures/Screenshots/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%28167%29.png)
![alt text](file:///c%3A/Users/freya666/Pictures/Screenshots/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%28169%29.png)
![alt text](file:///c%3A/Users/freya666/Pictures/Screenshots/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%28170%29.png)
![alt text](file:///c%3A/Users/freya666/Pictures/Screenshots/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%28171%29.png)


---

题目 3：[MoeCTF 2021] GET 请求理解

GET 请求知识点：
![alt text](file:///c%3A/Users/freya666/Pictures/Screenshots/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%28174%29.png)
解题过程：
![alt text](file:///c%3A/Users/freya666/Pictures/Screenshots/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%28174%29.png)
![alt text](file:///c%3A/Users/freya666/Pictures/Screenshots/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%28172%29.png)
![alt text](file:///c%3A/Users/freya666/Pictures/Screenshots/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%28173%29.png)


---

三、Linux 环境搭建与基础命令笔记

环境搭建方式：VMware 虚拟机

搭建步骤：

1. 下载 VMware Workstation 17 Player（免费版）
2. 下载 Ubuntu 22.04 LTS ISO 镜像
3. VMware 中点击“创建新虚拟机” → 选择 ISO 文件
4. 设置用户名、密码，分配 4GB 内存、50GB 磁盘空间
5. 完成安装后启动 Ubuntu

截图：
![alt text](file:///c%3A/Users/freya666/Pictures/Screenshots/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%28131%29.png)
![alt text](file:///c%3A/Users/freya666/Pictures/Screenshots/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%28132%29.png)
![alt text](file:///c%3A/Users/freya666/Pictures/Screenshots/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%28133%29.png)
![alt text](file:///c%3A/Users/freya666/Pictures/Screenshots/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%28136%29.png)
![alt text](file:///c%3A/Users/freya666/Pictures/Screenshots/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%28139%29.png)
![alt text](file:///c%3A/Users/freya666/Pictures/Screenshots/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%28141%29.png)
![alt text](file:///c%3A/Users/freya666/Pictures/Screenshots/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%28143%29.png)


---

Linux 基础命令学习笔记

文件与目录操作

命令 作用 示例
pwd 显示当前路径 pwd
ls 列出目录内容 ls -la
cd 切换目录 cd /home
mkdir 创建目录 mkdir test
rmdir 删除空目录 rmdir test
rm 删除文件/目录 rm -rf test
cp 复制文件 cp a.txt b.txt
mv 移动/重命名 mv a.txt b.txt
cat 查看文件内容 cat file.txt
less 分页查看文件 less large.log
head 查看文件开头 head -n 10 file.txt
tail 查看文件末尾 tail -n 20 file.txt

权限管理

命令 作用 示例
chmod 修改权限 chmod 755 script.sh
chown 修改所有者 chown user:group file

网络相关

命令 作用 示例
ifconfig / ip a 查看 IP 地址 ip a
ping 测试网络连通性 ping 8.8.8.8
curl 发送 HTTP 请求 curl http://example.com
wget 下载文件 wget http://example.com/file.zip

进程管理

命令 作用 示例
ps 查看进程 ps aux
top 实时查看资源 top
kill 终止进程 kill -9 PID

压缩与解压

命令 作用 示例
tar 打包/解包 tar -czvf archive.tar.gz folder/
unzip 解压 zip unzip file.zip

---

四、学习总结

本次学习完成了以下内容：

1. ✅ 安装并配置了 Burp Suite + 虚拟机 Firefox 代理抓包环境
2. ✅ 掌握了 F12 开发者工具、Hackbar、dirsearch 的基本使用
3. ✅ 完成了三道入门级 CTF 题目
4. ✅ 搭建了 VMware Ubuntu 虚拟机环境
5. ✅ 学习了 Linux 基础命令（文件操作、权限、网络、进程等）
