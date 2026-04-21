> ID：Tak3
>
> 方向：misc
>
> 日期：2026-04-19

Sagemath：

![img](https://cdn.nlark.com/yuque/0/2026/png/65087184/1776519974389-23a18ca2-afae-4357-90c6-23e1998071cf.png)

# 1. 基础知识

## 1.1. 质数（Prime Number）

又称素数，是指在大于![img](https://cdn.nlark.com/yuque/__latex/53072c2388d69edc65c2377681e4e87c.svg)的自然数中，除了![img](https://cdn.nlark.com/yuque/__latex/53072c2388d69edc65c2377681e4e87c.svg)和它本身以外不再有其他因数的的自然数。

## 1.2. 合数

合数可以看作由两个或多个素数相乘得到。

- 对于任意合数![img](https://cdn.nlark.com/yuque/__latex/df378375e7693bdcf9535661c023c02e.svg)，存在![img](https://cdn.nlark.com/yuque/__latex/79ce3c7a71877c2ff01695e38ade43ca.svg)个两两不同的素数![img](https://cdn.nlark.com/yuque/__latex/5b22ab4780484ac2b30b3edad2bc269f.svg)，使得![img](https://cdn.nlark.com/yuque/__latex/15c33713e0aa0e8834357fbaa722180a.svg)

## 1.3. 欧拉函数![img](https://cdn.nlark.com/yuque/__latex/17784a18a8ba11e0a4088389667d09a5.svg)

![img](https://cdn.nlark.com/yuque/__latex/17784a18a8ba11e0a4088389667d09a5.svg)是从![img](https://cdn.nlark.com/yuque/__latex/53072c2388d69edc65c2377681e4e87c.svg)到![img](https://cdn.nlark.com/yuque/__latex/df378375e7693bdcf9535661c023c02e.svg)中，与![img](https://cdn.nlark.com/yuque/__latex/df378375e7693bdcf9535661c023c02e.svg)互素（即![img](https://cdn.nlark.com/yuque/__latex/b86c952866eb5c64fa8416c27d3fb001.svg)）的整数![img](https://cdn.nlark.com/yuque/__latex/2443fbcfeb7e85e1d62b6f5e4f27207e.svg)的个数。

- 若![img](https://cdn.nlark.com/yuque/__latex/df378375e7693bdcf9535661c023c02e.svg)是素数，则![img](https://cdn.nlark.com/yuque/__latex/b3913c487f028e124d0aa988cfa4e368.svg)均与![img](https://cdn.nlark.com/yuque/__latex/d4cd21d60552e207f237e82def9029b6.svg)互素，所以有![img](https://cdn.nlark.com/yuque/__latex/2a902c456359ce130d7a34f28369bb23.svg)。
- 若![img](https://cdn.nlark.com/yuque/__latex/df378375e7693bdcf9535661c023c02e.svg)是由均为一次幂的两两不同的质数相乘所得的合数，即![img](https://cdn.nlark.com/yuque/__latex/15c33713e0aa0e8834357fbaa722180a.svg)，则有![img](https://cdn.nlark.com/yuque/__latex/9403e05b9bb77d5df356032296d1b527.svg)。

- 从![img](https://cdn.nlark.com/yuque/__latex/53072c2388d69edc65c2377681e4e87c.svg)到![img](https://cdn.nlark.com/yuque/__latex/df378375e7693bdcf9535661c023c02e.svg)共有![img](https://cdn.nlark.com/yuque/__latex/df378375e7693bdcf9535661c023c02e.svg)个数
- ![img](https://cdn.nlark.com/yuque/__latex/091a44b6adf69464fa153ab4fb6b1d64.svg)的倍数：![img](https://cdn.nlark.com/yuque/__latex/acc5a3fcf0d4ffaaa079fe6155b2a4fb.svg)，共有![img](https://cdn.nlark.com/yuque/__latex/47d373f456220e49024f4eeaa1597b0b.svg)个
- ![img](https://cdn.nlark.com/yuque/__latex/764c1c88fba43c220e26e27403bf676f.svg)的倍数：![img](https://cdn.nlark.com/yuque/__latex/ff3534716bfc1fa085b4a42e3b5085fa.svg)，共有![img](https://cdn.nlark.com/yuque/__latex/172ea62155907a1482b867a51d0c0f5f.svg)个
- ![img](https://cdn.nlark.com/yuque/__latex/40cd54342b6ff7c6045c77d0286ded13.svg)的倍数：![img](https://cdn.nlark.com/yuque/__latex/2925df5c09f579d8cdea77ab04870f07.svg)，共有![img](https://cdn.nlark.com/yuque/__latex/85f04e47f3136c0e468b2b91f701ed3e.svg)个
- 依次类推......
- ![img](https://cdn.nlark.com/yuque/__latex/17784a18a8ba11e0a4088389667d09a5.svg)本质上求的是从![img](https://cdn.nlark.com/yuque/__latex/53072c2388d69edc65c2377681e4e87c.svg)到![img](https://cdn.nlark.com/yuque/__latex/df378375e7693bdcf9535661c023c02e.svg)这从![img](https://cdn.nlark.com/yuque/__latex/df378375e7693bdcf9535661c023c02e.svg)个数中与![img](https://cdn.nlark.com/yuque/__latex/15c33713e0aa0e8834357fbaa722180a.svg)互质的数的个数，所以有![img](https://cdn.nlark.com/yuque/__latex/1860b0f230e6f556f33b2496444bbd3c.svg)

- 若![img](https://cdn.nlark.com/yuque/__latex/df378375e7693bdcf9535661c023c02e.svg)是合数且其因子存在素数的多次幂，即![img](https://cdn.nlark.com/yuque/__latex/52cc988f8f8a4a49cebd67ce50b4fc9b.svg)，则有![img](https://cdn.nlark.com/yuque/__latex/7a62dbfdadebdb258010b1a1c96b134f.svg)计算原理同上。

# 2. RSA

## 2.1. 概念

RSA 加密算法是一种非对称加密算法。

非对称加密算法：一种安全的数据加密方法，它使用一对密钥：公钥和私钥。公钥可以公开分享，而私钥必须保密。如果使用公钥加密数据，只有对应的私钥才能解密；反之亦然。这种加密方式因为使用了两个不同的密钥，因此被称为非对称加密。

RSA 算法的可靠性由极大整数因数分解的难度决定。

## 2.2. 基本原理

### 2.2.1. 生成密钥

1. 定义明文![img](https://cdn.nlark.com/yuque/__latex/4760e2f007e23d820825ba241c47ce3b.svg)、密文![img](https://cdn.nlark.com/yuque/__latex/b891664b42113aee13f0bac25eb998e5.svg)
2. 选两个大素数![img](https://cdn.nlark.com/yuque/__latex/d4cd21d60552e207f237e82def9029b6.svg)和![img](https://cdn.nlark.com/yuque/__latex/34c7b563b30bde3c748139530686798e.svg)
3. 计算![img](https://cdn.nlark.com/yuque/__latex/b45b467301bfb142f8413362f1579005.svg)
4. 计算欧拉函数![img](https://cdn.nlark.com/yuque/__latex/594ab9d5656399aed2069d1bb77b8c8c.svg)
5. 选一个与![img](https://cdn.nlark.com/yuque/__latex/17784a18a8ba11e0a4088389667d09a5.svg)互素的整数![img](https://cdn.nlark.com/yuque/__latex/c9a277d40d3a0b3afb85cdb557908945.svg)
6. 计算得到![img](https://cdn.nlark.com/yuque/__latex/c9a277d40d3a0b3afb85cdb557908945.svg)模为![img](https://cdn.nlark.com/yuque/__latex/17784a18a8ba11e0a4088389667d09a5.svg)的逆元![img](https://cdn.nlark.com/yuque/__latex/56c1b0cb7a48ccf9520b0adb3c8cb2e8.svg)，使得有![img](https://cdn.nlark.com/yuque/__latex/7dae8c7b5d4f59facc6117e783ea2b89.svg)

### 2.2.2. 加密与解密

1. 加密：![img](https://cdn.nlark.com/yuque/__latex/f3cafb854f9723cc4197713e73f9177b.svg)
2. 解密：![img](https://cdn.nlark.com/yuque/__latex/d95ade648d3239c602f259a177105e97.svg)

由此可以衍生出各种各样的 RSA 题的变体。

# 1. eeeeez_rsa

```python
from Crypto.Util.number import *
from secrets import randbits

p = getPrime(512)
q = getPrime(512)

n = p * q
e = 65537

m = bytes_to_long(flag)

c = pow(m, e, n)

print("p =", p)
print("q =", q)
print("e =", e)
print("c =", c)
'''
p = 7833526559350210716763736624276871338973265302039384005037668270722459749111510212645578582715412039060908556429504391788904499303021963918033838457712021
q = 11274522482114648167653425707657117942167215969612324249057858493398092816663094339833695146914712716091767834292452373966791325922322967827879446489910963
e = 65537
c = 10221721591889545844573050254595795861182348856506145605480348246534477032085113801390383245391427274224627900490105787486227774188957450006691363974396952878850785124275814042623413354128640305152567667226654321244510669777870256213487113315863197287562256336752636572876416053482569293397021584043886350655
'''
```

p 和 q 已知，利用欧拉函数求出 φ(n)，进而计算出 e 模 φ(n) 的逆元 d，由`m = pow(c,d,n)`求出明文，最终获得 flag。

## EXP

```python
import gmpy2
from Crypto.Util.number import long_to_bytes

p=7833526559350210716763736624276871338973265302039384005037668270722459749111510212645578582715412039060908556429504391788904499303021963918033838457712021
q=11274522482114648167653425707657117942167215969612324249057858493398092816663094339833695146914712716091767834292452373966791325922322967827879446489910963
e=65537
c=10221721591889545844573050254595795861182348856506145605480348246534477032085113801390383245391427274224627900490105787486227774188957450006691363974396952878850785124275814042623413354128640305152567667226654321244510669777870256213487113315863197287562256336752636572876416053482569293397021584043886350655

phi_n = (p-1)*(q-1)
d = gmpy2.invert(e,phi_n)
m = pow(c,d,p*q)
print(long_to_bytes(m))

# b'flag{W31c0m3_T0_Crypt0}'
```

从而得到 flag：`flag{W31c0m3_T0_Crypt0}`

# 2. What is dpdq

```python
from Crypto.Util.number import *

p = getPrime(512)
q = getPrime(512)

n = p * q

m = bytes_to_long(flag)

c = pow(m, e, n)

phi = (p - 1) * (q - 1)
d = inverse(e, phi)

dp = d % (p - 1)
dq = d % (q - 1)

print("p =", p)
print("q =", q)
print("dp =", dp)
print("dq =", dq)
print("c =", c)
'''
p = 7815414185491141116816659592648655093824828684096724566017773298150863675227130435782645950134326106977982747903113904523205447790009729530724322503221833
q = 9989016009119164140172559452397593815416653032520645020530362343604703571290641132626496035194681031089349635895258123948622879868985300264027551088746747
dp = 4010681140217557380422935065992638785960856284290416720391683347779267392850433355451759290094414691393922757792964689212573746434435619933431808206484225
dq = 2650091114188243387783699150080671432452650354401886796343461099352350290584408461982954461814393687345324352950407449243857759926179828428073409383707519
c = 49442655923625309909385017545371837339079019962533687954830521594031788193892512818961352203881969632046490177930759665200677302956816647378151364853230118743634390053041583940566732297636464662866406886764229490729837423276227228984024967061624432225315562131278455141688731687433597958272776740673914705069
'''
```

这道题是比较常见的 dp，dq 泄露

> 原本dp和dq的作用是用来加快加解密速度的,但是由于dp和p,dq和q的关系密切,一旦泄漏,将造成很大的安全隐患

一个比较粗糙的式子推导：

![img](https://cdn.nlark.com/yuque/0/2026/jpeg/65087184/1776606755995-b234d106-3521-42eb-a95b-8c57f6cc6cd9.jpeg)

## EXP

```python
import gmpy2
from Crypto.Util.number import long_to_bytes

p = 8637633767257008567099653486541091171320491509433615447539162437911244175885667806398411790524083553445158113502227745206205327690939504032994699902053229
q = 12640674973996472769176047937170883420927050821480010581593137135372473880595613737337630629752577346147039284030082593490776630572584959954205336880228469
dp = 6500795702216834621109042351193261530650043841056252930930949663358625016881832840728066026150264693076109354874099841380454881716097778307268116910582929
dq = 783472263673553449019532580386470672380574033551303889137911760438881683674556098098256795673512201963002175438762767516968043599582527539160811120550041
c = 24722305403887382073567316467649080662631552905960229399079107995602154418176056335800638887527614164073530437657085079676157350205351945222989351316076486573599576041978339872265925062764318536089007310270278526159678937431903862892400747915525118983959970607934142974736675784325993445942031372107342103852

q_inv=gmpy2.invert(q,p)
mp=pow(c,dp,p)
mq=pow(c,dq,q)
m=(((mp-mq)*q_inv)%p)*q+mq

print(long_to_bytes(m))
```



> 选择 Crypto 的原因：上一学期学了信息安全数学基础这门课，感觉这个方向跟这门课很贴近，所以想试试看 。