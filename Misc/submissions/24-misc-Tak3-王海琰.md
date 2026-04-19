> ID：Tak3
>
> 方向：misc
>
> 日期：2026-04-17
>

# 1. WriteUp

## 1.1. find_me

> 来源：[find_me](https://ctf.xidian.edu.cn/training/13?challenge=468)
>
> 题目描述：树师傅在自己最喜欢的照片里藏了flag，你能找出来吗？ 顺便一提，树师傅最喜欢的16进制编辑器是010 Editor。
>
> 工具：010Editor
>
> 附件：[📎find_me_attachments.zip](https://www.yuque.com/attachments/yuque/0/2026/zip/65087184/1776431311783-17e39faf-05ab-4590-8461-afa10d5fcea2.zip)
>

解压附件，得到名为`ssf.png`的 PNG 格式文件：

![img](https://cdn.nlark.com/yuque/0/2026/png/65087184/1776316335503-387e2eeb-1f9b-48c2-a4e4-e870a5763ebd.png)

根据题目描述的提示，使用`010Editor`打开该图片：

![img](https://cdn.nlark.com/yuque/0/2026/png/65087184/1776316553724-98fdb5f1-649d-4e7c-b9c6-a9a29a830601.png)

发现文件结束符`IEND`后面还有一段与 flag 格式相似的字符串：

![img](https://cdn.nlark.com/yuque/0/2026/png/65087184/1776316627455-2cfde839-3b87-463a-b028-b69523a8b740.png)

尝试将该字符串作为 flag 提交，响应通过：

![img](https://cdn.nlark.com/yuque/0/2026/png/65087184/1776316795817-6e9748e6-0417-43ce-83e5-c2578736cad6.png)

从而得到 flag：`moectf{hs_g1v3_u_fl@g}`

## 1.2. 金三胖

> 来源：[金三胖](https://buuoj.cn/challenges#金三胖)
>
> 题目描述：注意：得到的 flag 请包上 flag{} 提交
>
> 工具：StegSlove
>
> 附件：[📎77edf3b9-3ef9-4ead-9c81-ffdaf7a08414.zip](https://www.yuque.com/attachments/yuque/0/2026/zip/65087184/1776431311786-4cca1e7d-ad5d-4f3f-a09b-bfe2a8fd3a23.zip)
>

解压附件，得到名为`aaa.gif`的 GIF 格式文件：

![img](https://cdn.nlark.com/yuque/0/2026/gif/65087184/1776317330392-0f37173c-75c5-4063-b322-ba401e863fde.gif)

可见该 gif 图中有几张关键帧需要获取，使用 StegSlove 打开该文件并`分析`→`帧浏览器`：

![img](https://cdn.nlark.com/yuque/0/2026/png/65087184/1776336934126-362f8b84-bb59-4d03-9a54-3a04be1ffd60.png)

`<` `>`浏览，提取关键帧：

![img](https://cdn.nlark.com/yuque/0/2026/png/65087184/1776337004652-1310e9e2-3d20-47b7-aa7c-473e8dbe96f8.png)

![img](https://cdn.nlark.com/yuque/0/2026/png/65087184/1776337020112-9d815ac7-05ad-4051-8897-0539179e38d3.png)

![img](https://cdn.nlark.com/yuque/0/2026/png/65087184/1776337031796-a9cc1f28-33f0-4ead-bb87-6877edbf7cad.png)

拼接，从而得到 flag：`flag{he11ohongke}`

## 1.3. 大白

> 来源：[大白](https://buuoj.cn/challenges#大白)
>
> 题目描述：看不到图？ 是不是屏幕太小了 注意：得到的 flag 请包上 flag{} 提交
>
> 工具：010Editor
>
> 附件：[📎379140b0-c2aa-4aa6-b372-031beb2007f0.zip](https://www.yuque.com/attachments/yuque/0/2026/zip/65087184/1776431311783-798a9a14-c29f-4c84-82bb-318d3d147cd2.zip)
>

解压附件，得到名为`dabai.png`的 PNG 格式文件（直接放原图会报错，只能截图，下同）：

![img](https://cdn.nlark.com/yuque/0/2026/png/65087184/1776338199972-5f49e3cf-44cd-464d-afd4-7ecc3a84d528.png?x-oss-process=image%2Fcrop%2Cx_2%2Cy_2%2Cw_751%2Ch_762)

根据题目描述，考虑通过将图片调整至正常尺寸从而获得本题 flag，使用 010Editor 打开该文件：

![img](https://cdn.nlark.com/yuque/0/2026/png/65087184/1776338617849-6b576013-7c30-4fee-88a6-a5cdd5b09846.png)

注意到 IDHR 所在的`chunk [0]`出现 CRC 报错，且`IHDR`后的八个字节为`00 00 02 A7 00 00 01 00`，其中`00 00 02 A7`表示图片宽度，`00 00 01 00`表示图片高度，此时图片高度明显过小，推测为 CRC 报错的原因。使用 [IHDR-CRC](https://github.com/cmacckk/ihdr-crc) 爆破并直接生成结果图：

![img](https://cdn.nlark.com/yuque/0/2026/png/65087184/1776430454409-039ecc80-6af7-4c4a-b9c5-b153c03ffa4c.png)

```plain
python main.py -i dabai.png  //在当前目录下生成图片
```

![img](https://cdn.nlark.com/yuque/0/2026/png/65087184/1776430562631-5c2b5e7b-e255-4eaa-9219-85edb51b7974.png)

从而得到 flag：`flag{He1l0_d4_ba1}`

## 1.4. 寻找黑客的家

> 来源：[寻找黑客的家](https://ctf.xidian.edu.cn/training/13?challenge=477)
>
> 题目描述：大黑客Mikato期末结束就迫不及待的回了家，并在朋友圈发出了“这次我最早”的感叹。那么你能从这条朋友圈找到他的位置吗？
>
> moectf{照片拍摄地市名区名路名} (字母均小写) 例如：西安市长安区西沣路：moectf{xian_changan_xifeng}
>
> 工具：Microsoft Edge
>
> 附件：[📎Xun_Zhao_Hei_Ke_De_Jia__attachments.zip](https://www.yuque.com/attachments/yuque/0/2026/zip/65087184/1776431311782-2a9cdd84-aff9-4e31-b10b-552fb17c6965.zip)
>

解压附件，分别得到名为`附件1.png`的 PNG 文件和`附件2.jpg`的 JPG 文件：

![img](https://cdn.nlark.com/yuque/0/2026/png/65087184/1776340439692-cf2c3e77-8af5-480d-a252-e86e8b49e6e6.png)

![img](https://cdn.nlark.com/yuque/0/2026/jpeg/65087184/1776340440398-5ce64d58-06e6-46a5-8df8-1a94ee006620.jpeg)

使用 010Editor 打开这两张图片，没有得到什么有用的信息，只能通过图片判断照片的拍摄地点了。

发现关键词`汉明宫`，在百度地图上搜索该关键词，发现这样一处[街景](https://map.baidu.com/search/汉明宫/@12695157.76,2575498.39,21z,87t,135.24h?querytype=s&da_src=shareurl&wd=汉明宫&c=1&src=0&pn=0&sug=0&l=10&b=(12116711.301788531,2156116.6728960634;12546310.56762011,2404419.485754575)&from=webmap&biz_forward={"scaler":2,"styles":"pl"}&device_ratio=2#panoid=09005700122103101048384347E&panotype=street&heading=261.51&pitch=4.69&l=21&tn=B_NORMAL_MAP&sc=0&newmap=1&shareurl=1&pid=09005700122103101048384347E)：

![img](https://cdn.nlark.com/yuque/0/2026/png/65087184/1776341434161-7c125240-495a-4d60-acb7-6aa8e31836b9.png)

该街景地点在`深圳市龙华区清泉路`，不能说非常相似吧，只能说一模一样。提交 flag，响应通过：

![img](https://cdn.nlark.com/yuque/0/2026/png/65087184/1776341878420-16f9c1a3-d30f-4edf-9224-84589a55b4d7.png)

从而得到 flag：`moectf{shenzhen_longhua_qingquan}`

# 2. 工具部署

## 2.1. 010Editor

![img](https://cdn.nlark.com/yuque/0/2026/png/65087184/1776314759047-63a86679-7d04-4990-bf12-a98eb9f6e65c.png)

## 2.2. CyberChef

![img](https://cdn.nlark.com/yuque/0/2026/png/65087184/1776314823655-65d898e3-ac60-4075-9ae2-ea70d3b51034.png)

## 2.3. StegSolve

不知道为啥，导入 gif 图后不能正常浏览帧，这里使用的是[第三方修复版](https://github.com/souno-io/Stegsolve)。

![img](https://cdn.nlark.com/yuque/0/2026/png/65087184/1776319833395-d0de7d70-50d9-4f7f-a31b-f21c2f17ba24.png)

## 2.4. Python

![img](https://cdn.nlark.com/yuque/0/2026/png/65087184/1776314959567-7abfacb0-7ef4-4a0a-96f0-8bb10ca6226d.png)

## 2.5. IHDR-CRC

`IHDR-CRC`可对已知 IHDR 的 CRC 值爆破 PNG 的宽和高，并直接生成修复后的图片，[项目链接](https://github.com/cmacckk/ihdr-crc)。

![img](https://cdn.nlark.com/yuque/0/2026/png/65087184/1776430454409-039ecc80-6af7-4c4a-b9c5-b153c03ffa4c.png)

```plain
python3 main.py -i dabai.png  //不指定输出路径，在当前目录生成out.png
python3 main.py -i dabai.png -o res.png  //在指定路径生成res.png
```

题目涉及到的一些知识点，参考：https://b23.tv/D3tckZv

# 3. 知识点归纳

## 3.1. 图像文件格式

文件头：位于文件开头的一段承担一定任务的数据。它主要用于识别文件类型和记录文件的基本属性，系统和软件通常依靠它来正确解析文件。

文件尾：位于文件末尾的特定数据序列，用于标识文件数据的正常结束。在文件尾之后附加的数据通常不会被常规软件读取，因此常被利用来进行数据隐写。

| **文件类型**   | **文件头 (Header)**            | **文件尾 (EOF / Footer)** | **核心结构块 / 备注**                 |
| -------------- | ------------------------------ | ------------------------- | ------------------------------------- |
| **PNG 图片**   | `89 50 4E 47 0D 0A 1A 0A`      | `AE 42 60 82`             | `IHDR` (紧接文件头后，包含宽高数据)   |
| **JPEG 图片**  | `FF D8 FF E0` 或 `FF D8 FF E1` | `FF D9`                   | 无统一宽高块，多使用 Exif 或 Steghide |
| **GIF 动图**   | `47 49 46 38 39 61`            | `00 3B`                   | 多帧结构，适合隐藏碎片信息            |
| **ZIP 压缩包** | `50 4B 03 04`                  | `50 4B 05 06`             | 若藏于图片尾部，可直接修改后缀解压    |

### 3.1.1. PNG 图片

对于一个 PNG 文件来说，其文件头总是由位固定的字节来描述的，剩余部分由3个以上的 PNG 的数据块（Chunk）按照特定的顺序组成。

整体结构：

`文件头（sig）（89 50 4E 47 0D 0A 1A 0A）`＋`数据块（Chunk [0]）`＋`数据块（Chunk [1]）`＋`数据块（Chunk [2]）`＋......

文件头：用于标识文件类型。

数据块：PNG 定义了两种类型的数据块，一种称为**关键数据块**，共 4 个，这是标准的数据块，每个 PNG 文件都必须包含；另一种称为**辅助数据块**，这是可选的数据块。

| 数据块符号 | 数据块名称   | 多数据块 | 可选否 | 位置限制         |
| ---------- | ------------ | -------- | ------ | ---------------- |
| IDHR       | 文件头数据块 | 否       | 否     | 第一块           |
| PLTE       | 调色板数据块 | 否       | 否     | 在 IDAT 之前     |
| IDAT       | 图像数据块   | 是       | 是     | 与其他 IDAT 连接 |
| IEND       | 图像结束数据 | 否       | 否     | 最后一个数据块   |

对于每一个数据块都有着统一的数据结构，每个数据块由 4 个部分组成。

| 名称                            | 字节数   | 说明                                                         |
| ------------------------------- | -------- | ------------------------------------------------------------ |
| Length（长度）                  | 4 字节   | 指定数据块中数据域的长度                                     |
| Chunk Type Code（数据块类型码） | 4 字节   | 由 ASCII 字母（`A-Z`、`a-z`）组成                            |
| Chunk Data（数据块数据）        | 可变长度 | 粗出按照 Chunk Type Code 指定的数据                          |
| CRC（循环冗余检测）             | 4 字节   | 存储用来检测是否有错误的循环冗余码。其域值由 Chunk Type Code 域和 Chunk Data 域中的数据计算所得，两者任一的信息错误军会导致 CRC 报错 |

#### 3.1.1.1. sig

![img](https://cdn.nlark.com/yuque/0/2026/png/65087184/1776401864560-68a1ada7-1cce-489d-9237-84ee88e28ff6.png)

长度为 8 字节，每种文件与之对应一段固定的 sig 码。错误改动 sig 会导致图片无法正常显示，将 sig 正确修改后可正常显示。

#### 3.1.1.2. IDHR

![img](https://cdn.nlark.com/yuque/0/2026/png/65087184/1776401851389-5f26b5f4-8e34-4448-ae7e-5c9f827e1a60.png)

- `文件头数据块 IDHR（Image Header Chunk）`：包含 PNG 文件中存储的图像数据的基本信息，长度为 13 字节，并作为第一个数据块出现在 PNG 数据流中，且一个 PNG 数据流中只能有一个 IDHR
- 一般只关注前 8 字节（标识图片宽和高）的内容
- 我们经常会去更改一张图片的高度或宽度使得一张图片显示不完整，从而达到隐藏信息的目的

| 域的名称 | 字节数  | 说明                   |
| -------- | ------- | ---------------------- |
| Width    | 4 Bytes | 图像宽度，以像素为单位 |
| Height   | 4 Bytes | 图像高度，以像素为单位 |

#### 3.1.1.3. IDAT

![img](https://cdn.nlark.com/yuque/0/2026/png/65087184/1776402157174-74ecacbf-2707-42f2-9c02-ef6917d273e9.png)

- `图像数据块 IDAT(Image Data Chunk)`：在实际数据流中多个连续存在，存储实际图像数据
- 存储图像数据
- 多个连续顺序存在于数据流中
- 采用 LZ77 算法的派生算法进行压缩
- 可以使用 zlib 解压缩
- 只有当上一个 IDAT 数据块填充满时，才会继续一个新的块

#### 3.1.1.4. IEND

![img](https://cdn.nlark.com/yuque/0/2026/png/65087184/1776402173436-f48ae37e-2e52-4b49-8458-30ad9f72811c.png)

- `图像结束数据块 IEND（Image Trailer Chunk）`：标记 PNG 文件或者数据流已经结束，并且必须要放在文件尾部
- `00 00 00 00 49 45 4E 44 AE 42 60 82`
- IEND 数据块的长度总是`00 00 00 00`，数据标识总是 IEND `49 45 4E 44`，因此，CRC 码也总是`AE 42 60 82`
- 可在 IEND 数据块后添加要隐藏的信息

## 3.2. CRC 校验

循环冗余校验（Cyclic Redundancy Check，CRC）是一种用于检测数据传输或存储过程中错误的技术。它通过对数据进行除法运算并计算余数来实现错误检测。

对一张正常的图片，通过修改其宽度或者高度隐藏信息，使计算出的 CRC 校验码与原图的 CRC 校验码不一致；Windows 的图片查看器会忽略错误的 CRC 校验码，因此会显示图片，但此时的图片已经是修改过的，所以会有显示不全或扭曲等情况，借此可以隐藏信息。

`IHDR-CRC`可对已知 IHDR 的 CRC 值爆破 PNG 的宽和高，并直接生成修复后的图片。