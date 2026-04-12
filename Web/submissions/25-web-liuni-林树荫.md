

## 📝 个人信息
* [cite_start]**ID:** liuni
* [cite_start]**方向:** Web 安全 
* [cite_start]**日期:** 2026-04-12 
* [cite_start]**常用 AI 助手:** Gemini 
---

## 🚩 CTF 题目实战记录

### 1. 签到题
* [cite_start]**Flag:** `NSSCTF {We1c0me_t0_WLLMCTF_Th1s_1s_th3_G1ft}` 
* [cite_start]**解题思路:** 直接查看网页源代码（F12 查看 HTML），Flag 隐藏在注释或标签中。 
![](1.png)
### 2. 隐藏入口 (secret.php)
* [cite_start]**Flag:** `NSSCTF {0c659c79-c056-4932-870b-295b483de96d}` [cite_start]**解题思路:** 题目提供 `secret.php`，通过输入框触发回车进入后台，获取账号密码登录后获取 Flag。 
* ![](2.png)
* ![](3.png)
* ![](4.png)
### 3. 青少年CTF - robots 协议
* [cite_start]**Flag:** `flag{97fd01137dfe40088cfe1967be421d84}` * [cite_start]**解题思路:** * 访问 `robots.txt` 寻找敏感路径。     * [cite_start]根据提示发起 GET 请求，当参数满足 `?moe=flag` 时返回 Flag。 
* ![](5.png)
---

## 🛠️ Web 安全工具箱

| 工具名称 | 获取途径 / 说明 |
| :--- | :--- |
| **Hackbar** | [cite_start]从 GitHub 下载免费版，通过 Firefox 插件安装。
| **Burp Suite** | [cite_start]核心抓包工具，从网上获取。
![]（6.png)
![]（7.png）
| **Dirsearch** | [cite_start]目录扫描工具，从 GitHub 官方仓库下载。 
---
![]（8.png）
## 🐧 Linux 系统环境搭建
1.  [cite_start]**选择发行版**：选择 Ubuntu 官方长期支持版 (LTS)。
2.  [cite_start]**安装流程**：从 Ubuntu 官网下载镜像，通过虚拟机或物理机安装。
3.  **后续配置**：更新软件源，安装常用工具包。

---

## 💻 Linux 基础命令学习笔记

### 1. 文件与目录操作
| 命令          | 功能描述                          |
| :---------- | :---------------------------- |
| `ls`        | [cite_start]列出当前目录内容          |
| `cd`        | [cite_start]切换工作目录            |
| `pwd`       | [cite_start]显示当前所在路径          |
| `mkdir`     | [cite_start]创建新目录             |
| `rm`        | [cite_start]删除文件或目录           |
| `cp` / `mv` | [cite_start]复制 / 移动或重命名文件/文件夹 |

### 2. 系统信息与进程管理
| 命令 | 功能描述 |
| :--- | :--- |
| `top` | [cite_start]实时监控系统资源占用（CPU、内存等） ||
`ps -ef` | [cite_start]查看当前系统所有运行中的进程快照  |
| `df -h` | [cite_start]以易读格式查看磁盘空间使用情况  |
| `free -m` | [cite_start]以 MB 为单位查看内存使用情况  |

### 3. 权限管理与文本处理
| 分类 | 命令 | 功能描述 |
| :--- | :--- | :--- |
| **权限** | `chmod` | [cite_start]修改文件或目录的访问权限  |
| | `chown` | [cite_start]修改文件/目录的所有者  |
| | `sudo` | [cite_start]以超级管理员权限执行命令 |
| **文本** | `cat` | [cite_start]在终端直接输出文件完整内容  |
| | `grep` | [cite_start]在文本中搜索指定的字符串/模式  |
| | `vim` | [cite_start]强大的终端文本编辑器  |

---
