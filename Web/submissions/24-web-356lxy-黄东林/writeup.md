# writeup 神奇的F12
- ID：黄东林
- 方向：web
- 日期：2026.4.17晚
- 平台：NSS
- 题目：[SWPUCTF 2021 新生赛gift_F12SWPUCTF 2021 新生赛gift_F12](https://www.nssctf.cn/problem/382)

## 目标与范围
- 漏洞类型：**源码泄露**
- 约束与规范：仅在授权范围内操作

## 解题过程
1. 题目提醒**F12**
2. 点击F12查看源代码  
![](https://cdn.nlark.com/yuque/0/2026/png/42700124/1776437670671-72d2fc90-80af-4b23-9d92-4b6a272bf08c.png)
3. 写入flag：NSSCTF{We1c0me_t0_WLLMCTF_Th1s_1s_th3_G1ft}

## 关键操作
- 点击**F12** 
# writeup robots
- ID：黄东林
- 方向：web
- 日期：2026.4.17晚
- 平台：青少年CTF
- 题目：[robots.txt](https://www.qsnctf.com/#/main/driving-range?page=1&category=&difficulty=&keyword=robots.txt&user_answer=&user_favorite=&tag_ids=)

## 目标与范围
- 漏洞类型：**信息泄露**
- 仅在授权范围内操作

## 解题过程  
1. 先用AI了解下robots.txt是什么意思。
2. 然后在网站根目录输入/robots.txt
3. 逐个代入/login.php
禁用:/admin.php
不允许:/secret.php
找到flag
4. 第一题
![](https://cdn.nlark.com/yuque/0/2026/png/42700124/1776440397359-aebd9a95-d870-4501-b42b-ccdc687510ba.png)
5. 第二题
![](https://cdn.nlark.com/yuque/0/2026/png/42700124/1776440514794-55017bbb-1218-4c7d-b297-dce93d76b45b.png)


## 关键操作 
-了解robots.txt含义，代入根目录
- 找到隐藏了账号密码的目录

