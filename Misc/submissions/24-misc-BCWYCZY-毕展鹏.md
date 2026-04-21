### 1，find me
解压发现是一个图片

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/65054250/1776053348181-a85b832a-bd2b-4c26-b0e1-a1609d7a9136.png)

拖进010editor后查找字符串

拖到最后发现

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/65054250/1776053392461-c7538ad7-3f3e-43b0-b728-7774aa261f97.png)

输入网站shell

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/65054250/1776053430258-a273ff62-ff0e-40a5-8096-8f49c52a75fc.png)

成功

### 2，金三胖
解压发现是一个gif动图，且闪烁出现flag字段

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/65054250/1776053743771-f68e4cf1-4e3c-4367-814a-3e59e5387470.png)

在达芬奇里面逐帧查看得到完整flag

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/65054250/1776053767765-68de5c9a-53bc-427f-a533-bcac295038b4.png)<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/65054250/1776053780469-c3179277-0aef-42dc-abc3-73649d2ead7b.png)<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/65054250/1776053791164-7351536f-464c-425c-8a13-923f7c4b1183.png)

成功

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/65054250/1776053819451-1c9e7426-99e3-4ef0-8d28-4307908715de.png)

### 3，大白
根据提示可知应该要修改图片长宽高度

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/65054250/1776053863464-0415d836-7007-48b5-b281-652a76d5a52d.png)

解压得到图片明显高度被人为修改过

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/65054250/1776054058996-37b5d7f0-30d8-4bbc-ab41-6267b47d061c.png)

010editor修改高度

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/65054250/1776054032946-a90b6c34-d606-469a-bd01-f8cb2e0f69d1.png)<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/65054250/1776054081253-b0a9961f-dcbf-4acf-a00f-c1609b7879f2.png)

得到flag

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/65054250/1776054092511-ec2f9c2d-ba46-4abd-8a32-31116c54d300.png)

成功

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/65054250/1776054135160-b327025e-b113-4a93-bf9c-15c11495c522.png)

### 4，<font style="color:rgb(0, 0, 0);">寻找黑客的家</font>
<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/65054250/1776054361625-d818ab4d-d128-4918-90e9-2a7517deefd6.png)

解压得到图片的明显特征为汉明宫商铺

高德地图搜索

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/jpeg/65054250/1776054423602-114c4aaf-7cf4-4283-af61-22f3fe20b9a4.jpeg)<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/jpeg/65054250/1776054421134-a6095259-3455-4bc7-a7a6-55f95080ab7f.jpeg)

边上的店铺和图片中一致，地点为深圳市龙华区清泉路

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/65054250/1776054489323-eda991b5-f3ea-45b7-b1f9-994d44e902e1.png)

成功



### 个人练习
#### 1，小明的保险箱
阅读提示

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/65054250/1776054662083-74ec332e-5ed5-4828-b114-ba5a21d5dd96.png)

解压是一个图片

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/65054250/1776055036470-62cc4d9f-5e76-4f1f-a5cb-d77d9b00fb7f.png)

010editor打开发现一个网页

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/65054250/1776055044040-da184cc5-4450-42ef-a15b-a95c8cdc229d.png)

404说明不对

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/65054250/1776055097649-15b7b567-1385-40fc-835f-ea1b653a4aa3.png)

提示说4位数字有可能隐藏了压缩包

使用binwalk进行分离

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/65054250/1776055620421-bac903c1-dbd7-478d-a137-e53008e220ba.png)

得到压缩包

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/65054250/1776055647913-e12c14ac-4923-4ba3-8068-5107f305667d.png)

使用ARCHPR暴力破解数字密码

得到7869

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/65054250/1776055725100-de45aa6b-d303-4f33-af21-b28981f75364.png)

解压得到一个txt，打开

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/65054250/1776055791419-e4163f1e-43a6-4c50-8998-92f07a0f210b.png)

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/65054250/1776055779708-84f665d9-d431-4364-b577-f3b43cd7d5d6.png)

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/65054250/1776055757338-a6ca087d-6fd4-45c0-925a-9b942fc3412a.png)

成功

#### 2,easycap
解压发现是一个流量包，WireShark打开

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/65054250/1776571738899-0fdb64ee-8f7d-4ba7-9c48-87662ea90d32.png)

字符串查flag查不到

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/65054250/1776571848646-e22ae323-14e3-4dd2-93db-9ab4d24855e4.png)

追踪随便一个流试试

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/65054250/1776571769680-b544f0f5-756a-4ff5-8f17-d393a3c28cc1.png)

竟然成功

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/65054250/1776571874409-bf3b62d8-f771-4461-9c65-cf3392b1f00a.png)

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/65054250/1776571904875-7ed322f9-7479-4e9e-b77e-0a93bf6b3b41.png)

#### 3，隐藏的钥匙
解压发现是一个图片

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/65054250/1776572070099-e11d0784-5b64-4833-8ee3-385b270dc77e.png)

010editor打开

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/65054250/1776572085261-71fc00ad-f0d8-43fb-b9cc-f1e4595cef38.png)

直接搜索text flag

提示说要base64

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/65054250/1776572111767-2906f1c7-0d78-4e35-a2a4-6a93c4c820eb.png)

cyberchef解密<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/65054250/1776572166347-40ac27de-8b29-4691-a874-fa11ddec3adf.png)

成功

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/65054250/1776572142039-d26112ce-4979-44b5-b90c-56d941f7a13c.png)

