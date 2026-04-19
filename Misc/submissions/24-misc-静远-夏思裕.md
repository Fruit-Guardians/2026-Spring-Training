# 一.配置环境

## 1.010Editor
<img width="1885" height="1260" alt="屏幕截图 2026-04-17 175720" src="https://github.com/user-attachments/assets/e33c21c1-7709-42e5-8f36-7d5a626a639c" />

## 2.CyberChef
<img width="1834" height="1508" alt="屏幕截图 2026-04-17 180222" src="https://github.com/user-attachments/assets/156b0be5-fcdb-4877-a402-c74f5a31d00e" />

## 3.Dev cpp
<img width="1724" height="1112" alt="屏幕截图 2026-04-17 182436" src="https://github.com/user-attachments/assets/2dd324c9-f2a6-4a46-8ac6-498261a4d8fa" />

# 二.解题

## 1.find_me
<img width="306" height="432" alt="ssf" src="https://github.com/user-attachments/assets/2e8d4d1c-a409-44b5-9094-277aacb15d45" />

+ 题目描述：树师傅在自己最喜欢的照片里藏了flag，你能找出来吗？ 顺便一提，树师傅最喜欢的16进制编辑器是010 Editor。

> 根据题目描述可知，本题需要用到010Editor作为工具,Thus,我们把图片导入010Editor
>
> <img width="1482" height="1042" alt="屏幕截图 2026-04-17 212650" src="https://github.com/user-attachments/assets/014b57e1-0e1d-4ec9-9e1b-fee0e36176e2" />
>
> 直接以搜索文本的方式搜索flag{ 发现并没有找到,但ZiPbt模板识别里面藏了一个ssf.png文件，基本可以确定flag大概率就藏在这里。
>
> SO,我们把它提取出来
> 
> <img width="1518" height="1063" alt="屏幕截图 2026-04-17 213933" src="https://github.com/user-attachments/assets/270238cc-eb72-4056-a598-194674f10b7f" />
>
> 把它导入010Editor,并再次搜索flag{ 发现还是找不到
>
> <img width="1517" height="1052" alt="屏幕截图 2026-04-17 214134" src="https://github.com/user-attachments/assets/1b3b32e5-8b6c-41fb-81a2-02064224d6af" />
>
> 奇了怪了，去看看文件数据尾部
>
> <img width="1511" height="1043" alt="屏幕截图 2026-04-17 214738" src="https://github.com/user-attachments/assets/9d2c68e9-cc7c-48c5-bae7-13de847ead79" />
>
> 发现正确答案moectf
>
> 提交flag,Correct!
>
> <img width="1378" height="248" alt="屏幕截图 2026-04-17 215004" src="https://github.com/user-attachments/assets/5e8919b0-89b7-48db-a797-8db37b63fbe1" />

## 2.金三胖
<img width="219" height="186" alt="aaa" src="https://github.com/user-attachments/assets/553cf8e9-b735-4df5-bb5d-6a5d59f49735" />

+ 发现文件格式是gif，有几帧红色的部分我似乎看到了flag字样，于是我打算对它进行逐帧查看（不知道为什么我的StegSolve总是把它识别成普通图片，于是我只好换了个可以逐帧查看动图的网站...)

> <img width="747" height="905" alt="屏幕截图 2026-04-17 220649" src="https://github.com/user-attachments/assets/6f8ed6c0-7449-4836-8209-285d888fa73d" />
>
> <img width="1827" height="1340" alt="屏幕截图 2026-04-17 223821" src="https://github.com/user-attachments/assets/730021f0-241c-4f1c-abbd-acc14eb99a7c" />
>
> <img width="1831" height="1391" alt="屏幕截图 2026-04-17 230052" src="https://github.com/user-attachments/assets/dcdd21f5-42cf-4244-afed-fc261e1ddbcc" />
>
> <img width="1829" height="1389" alt="屏幕截图 2026-04-17 230144" src="https://github.com/user-attachments/assets/fe132e80-3e49-4a48-ba3a-034d8fef8657" />
>
> 提交wp,Correct.
>
> <img width="777" height="588" alt="屏幕截图 2026-04-17 231638" src="https://github.com/user-attachments/assets/5f8d9562-5c79-4283-bb74-fa7adaf02411" />

## 3.大白
<img width="679" height="256" alt="dabai" src="https://github.com/user-attachments/assets/17704061-f725-44ec-b727-5475c993a940" />

+ 题目描述：看不到图？ 是不是屏幕太小了

> 根据题目描述，不难得出，可能是图片的大小被做了手脚，这里我们依旧将其导入010Editor
>
> <img width="1477" height="1041" alt="屏幕截图 2026-04-17 232754" src="https://github.com/user-attachments/assets/337c921d-894e-4600-b557-8559d08ec5d2" />
>
> 注意到，图片的高度明显小于其宽度，试试把它的高度改成和宽度一样
>
> <img width="1485" height="1032" alt="屏幕截图 2026-04-17 234237" src="https://github.com/user-attachments/assets/f23c2779-9898-4026-a812-33174041da06" />
>
> 再次打开图片看看
>
> <img width="765" height="536" alt="屏幕截图 2026-04-17 234307" src="https://github.com/user-attachments/assets/6dba87e2-96da-4391-b1a3-8a2425ce13df" />
>
> wp果然就藏在图片下方
>
> 提交wp,Correct.
>
> <img width="775" height="622" alt="屏幕截图 2026-04-17 234508" src="https://github.com/user-attachments/assets/2e2eeff7-b017-4374-83de-f161774551db" />

## 4.寻找黑客的家
<img width="1080" height="1440" alt="附件1" src="https://github.com/user-attachments/assets/834c5f2e-9bbf-431f-91f4-5aa8a6448b90" />

<img width="1440" height="1471" alt="附件2" src="https://github.com/user-attachments/assets/3dd8ea1e-242d-4d3d-808c-b2c87a1275c8" />

> 这种找街景的题我就不去各大地图软件搜了，我选择优先喂AI
>
> <img width="1836" height="1392" alt="屏幕截图 2026-04-17 235901" src="https://github.com/user-attachments/assets/78b0e604-9100-4b04-95a1-7c7ff1024b18" />
>
> 尝试性地提交wp,Correct.
>
> <img width="1421" height="266" alt="屏幕截图 2026-04-18 000046" src="https://github.com/user-attachments/assets/20cc8b8b-9ae8-4fb5-9992-f885946153b8" />

# 三.总结

1. Misc图片类的题经常在图片文件数据中藏zip,而题解经常藏在文件数据的开头或者结尾处
2. Misc动图类的题经常把题解藏在几个关键帧中，可以用StegSolve等工具对其进行逐帧分析
3. 图片的大小数据可能会被修改，以后遇到那种图片大小很奇怪的可以留意一下
4. 个人认为街景类的题可以优先喂AI，可以省去不少时间
