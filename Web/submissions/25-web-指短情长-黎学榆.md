# 第一题
我在里面找了半天不知道题目是什么意思。看了下讨论区才知道要找靶场。问了豆包才知道要找出flag是哪一行代码。
在讨论区里看到有个人的截图才知道要用浏览器的工具才能显示源代码。我一行一行找，一个个展开才找到flag在哪。  
1.花费10金币开启靶机，点击链接跳转到一个页面  
2.用浏览器的"开发人员工具"显示代码  
3.找到flag  
4.复制flag到解题框里  
5.把括号外的WLLM改为NSS   
![](https://raw.githubusercontent.com/38yu/image/refs/heads/main/25-web-%E6%8C%87%E7%9F%AD%E6%83%85%E9%95%BF-%E9%BB%8E%E5%AD%A6%E6%A6%86/%E5%9B%BE%E7%89%877.png)  
# 第二题
这题我先看了别人的writeup知道这题不是在代码里找flag。然后问了AI才明白使用浏览器网址栏搜索框  
1.点击下发赛题，显示出网址，点击网址  
2.进入页面后，在网址后加/robots.txt  
3.会显示3个选项选择secret那个  
4.在网址删去robots.txt后，在加/secret.php  
5.得到账户和密码，再返回首页登录即可拿到flag  
![](https://github.com/38yu/image/blob/main/25-web-%E6%8C%87%E7%9F%AD%E6%83%85%E9%95%BF-%E9%BB%8E%E5%AD%A6%E6%A6%86/%E5%9B%BE%E7%89%873.png?raw=true)    
![](https://github.com/38yu/image/blob/main/25-web-%E6%8C%87%E7%9F%AD%E6%83%85%E9%95%BF-%E9%BB%8E%E5%AD%A6%E6%A6%86/%E5%9B%BE%E7%89%874.png?raw=true)  
# 第三题
我直接问Ai这段代码怎么找到flag    
1.开启靶场，点击链接跳转到代码页面  
2.在网址框原网址后面输入/?moe=flag便得到flag  
！[](https://github.com/38yu/image/blob/main/25-web-%E6%8C%87%E7%9F%AD%E6%83%85%E9%95%BF-%E9%BB%8E%E5%AD%A6%E6%A6%86/%E5%9B%BE%E7%89%876.png?raw=true)  
# Linux和bursuit我之前学过一点便也就安装好了。但我装的是kali的。   
1.！[](https://github.com/38yu/image/blob/main/25-web-%E6%8C%87%E7%9F%AD%E6%83%85%E9%95%BF-%E9%BB%8E%E5%AD%A6%E6%A6%86/%E5%9B%BE%E7%89%871.png?raw=true)  
2.！[](https://github.com/38yu/image/blob/main/25-web-%E6%8C%87%E7%9F%AD%E6%83%85%E9%95%BF-%E9%BB%8E%E5%AD%A6%E6%A6%86/%E5%9B%BE%E7%89%878.png?raw=true)
