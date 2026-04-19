## 第一题：find me

#### 图片放入010editor

![](https://r2.image-upload.app/tyImg/1fz1bfxIn.png)

#### 将最后的IEND数据重新输入进010editor

![](https://r2.image-upload.app/tyImg/ekC1nVRy.png)

#### 找到所需flag：moectf{hs_g1v3_u_fl@g}

------

## 第二题：金三胖

#### 将gif图放入stegsolve并使用帧分析功能

![](https://r2.image-upload.app/tyImg/15NSPrWxF.png)

#### 逐帧查看，找到所需的flag码

![](https://r2.image-upload.app/tyImg/1epyVIkw7.png)

![](https://r2.image-upload.app/tyImg/wC51NL7S.png)

![](https://r2.image-upload.app/tyImg/19HH0eVfP.png)

#### 找到flag码：flag{hello hongke}

------

## 第三题：大白

![](https://r2.image-upload.app/tyImg/tFBFeZkg.jpg)

#### 由题目与图片提示，可能图片并未显示完全，将图片放入010editor

![](https://r2.image-upload.app/tyImg/yD46aPW0.png)

#### 发现高度过低，将高度也调整成”00 00 02 A7“

#### ![](https://r2.image-upload.app/tyImg/KTpTNqO4.png)

#### 得出所求flag：flag{He1lo_d4_ba1}

------

## 第四题：寻找黑客的家

#### 由第一张图有“汉明宫”店铺，进入百度地图查看街景，在深圳市龙华区清泉路发现类似建筑

![](https://r2.image-upload.app/tyImg/4imtj1h4.png)

#### 填入答案为：moectf{shenzhen_longhua_qingquan}

------

## 工具配置

#### python

![](https://r2.image-upload.app/tyImg/3FpwBACF.png)



#### Cyber chef

![](https://r2.image-upload.app/tyImg/10Arlq15Y.png)

#### 16进制编辑器

![](https://r2.image-upload.app/tyImg/yD46aPW0.png)

------

## 知识归纳

#### 1.010editor导入图片后，注意观察首部和尾部，尾部IEND可能有隐写。

#### 2.010editor导入png形式的图片，在16-19位置是图片的宽度，20-23位置是图片的高度，发现图片有截图迹象时要注意改变高宽找到隐藏信息。

#### 3.steg solve 中的Frame Browser功能可以逐帧查看GIF，发现GIF图中的信息。