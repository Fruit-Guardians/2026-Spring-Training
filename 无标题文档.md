# 环境搭建
## 1.IDA Pro的安装和基本配置
<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/67835331/1777205234753-28c18028-d589-463a-90b9-7d2476a62e26.png)

## 2.Linux虚拟机的安装
<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/jpeg/67835331/1777205817273-b6de6d28-25c4-42a0-acc6-a5fad8f615a2.jpeg)

## 3.c语言和python的搭建
<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/67835331/1777205832561-d0ad0a59-7ee2-48ff-bdae-57b07f248545.png)<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/67835331/1777205832856-4d381bab-680b-4504-bd18-5d68a466e377.png)

## 4.Jadx的安装
<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/jpeg/67835331/1777205852208-8fec33bf-d810-466b-a072-67303c2f5632.jpeg)

# 逆向工程和WriteUp
## begin
### 将程序通过ida打开显示的是汇编语言，根据提示按F5生成c语言的伪代码
<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/67835331/1777205911570-0207cddd-98fc-4c77-a779-927ec947e56c.png)

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/67835331/1777205870852-248ae686-00ed-436f-ad22-168344f6c217.png)

### 根据提示发现flag part1是乱码，按a将16进制转换成字符串即可得到第一部分
<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/67835331/1777205871030-4c84f2b6-8922-4310-878d-03b7c653bd4f.png?x-oss-process=image%2Fformat%2Cwebp)

### 根据提示按shift+F12整理出程序所有的字符串
<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/67835331/1777205925759-058a3ff5-12fd-4103-a8d9-75f13571942f.png)

### 找到flag part2
<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/67835331/1777205939858-d44c3f2f-4d41-4ed6-bbee-2d12bc353d26.png)

### 再根据提示发现flag part2被交叉引用，选中flag part2按X找到调用flag part2的函数，函数名就是flag part3
<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/67835331/1777205957575-474e09b9-7060-484a-a92c-11b79eff1e17.png)<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/67835331/1777205957599-fb94c392-840a-411d-9c0c-a7801fc67878.png)

### 组合到一起找到flag{Mak3_aN_3Ff0rt_tO_5eArcH_F0r_th3_f14g_C0Rpse}


