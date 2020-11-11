****
# 题库微信小程序
注：切勿将 `服务器网页端` 文件夹和`remade`文件夹(这里本意是readme,打错了，改改好费劲，就这样了)放入 `微信开发者工具`，使用的时候注意分开，除了这个文件夹，其他的都可以放入`微信开发者工具`
****
# 目录
* [声明](#声明)
* [一、哔哩哔哩教程](#一哔哩哔哩教程)
* [二、项目工程下载 国内源](#二项目工程下载国内源)
* [三、导入自定义题库网址](#三导入自定义题库网址)
* [四、有问题可以联系我](#四有问题可以联系我)
* [五、微信扫码打开小程序可进行体验](#五微信扫码打开小程序可进行体验)
* [六、小程序端配置步骤](#六小程序端配置步骤)
* [七、自定义题库模块说明](#七自定义题库模块说明注意)
* [八、服务器网页端说明](#八服务器网页端说明)
* [九、自定义题库题目格式说明](#九自定义题库题目格式说明)
* * [1.自定义题库示例文件](#1自定义题库示例文件)
* * [2.题库格式帮助视频](#2题库格式帮助视频)
* * [3.题库格式Excel示例](#3题库格式Excel示例)
* [十、自带题库格式说明](#十自带题库格式说明)
* * [1.自带题库示例文件](#1自带题库示例文件)
* [十一、关于遇到的问题](#十一关于遇到的问题)
* * [1.自带题库题目加载不出来](#1自带题库题目加载不出来)
* * [2.换行符问题](#2换行符问题)
* * [3.如何去除导入题库模块](#3如何去除导入题库模块)
* * [4.如何删除广告位](#4如何删除广告位)
* * [5.导入题库后乱码](#5导入题库后乱码)
* * [6.如何快速锁定题库文件错误位置](#6如何快速锁定题库文件错误位置)
* [关于](#关于)
****

## 声明
### 此项目参加过2019微信小程序开发大赛，华东赛区二等奖。
### 禁止利用此项目参赛，否则后果自负！！！ 
### 由于GitHub有时候会被GFW误'墙'，或者种种原因，本页面图片会不显示，可以选择点图片（不显示图片，但文字一定会显示的）进去，然后下载下来看。或者对着本页面空白处，右击，另存为，弹出的窗口下面选择`网页，全部(* htm,* html)`,然后打开下载的html文件可正常观看（头部会有一大串乱乱的排版，不要紧，往下拉，下面正常的）。
### 使用本项目上线时请声明：开源项目，来自https://github.com/547414/tkwxxcx
### 源码我也没有收费，保留原作者版权也是[MIT协议](https://baike.baidu.com/item/MIT/10772952)所规定的。这也是对作者的一种尊重，让作者有继续开发的动力。

****
### 一、哔哩哔哩教程
新版本（本项目）：https://www.bilibili.com/video/BV1zf4y1S7oF  
老版本：https://www.bilibili.com/video/BV1fb411a71B  
****
## 二、项目工程下载(国内源）
由于Github国内下载慢，特提供以下下载源(蓝奏云)，包括老版本工程文件  
https://crysu.lanzous.com/b09rfxhzc
密码:`7vt9`
****
### 三、导入自定义题库网址
https://crysu.com/zhddktk/
****
### 四、有问题可以联系我
QQ: `2686885195`  
邮箱：`crysu@crysu.com`或`zbshr@foxmail.com`  
相关文件下载：https://cloud.crysu.com/题库微信小程序[小窝刷题]  
****
## 五、微信扫码打开小程序可进行体验
或者微信搜索`小窝刷题`也可进行体验  
  
![Image text](https://raw.githubusercontent.com/547414/tkwxxcx/master/remade/zhddktk.jpg)
****
## 六、小程序端配置步骤
### 1.点击本页面绿色的`code`按钮，然后点`Download ZIP`下载本项目`（tkwxxcx-master）`  
### 2.解压后得到`tkwxxcx-master`文件夹，删除其中的 `服务器网页端` 文件夹和`remade`文件夹  
### 3.将项目`（tkwxxcx-master）`导入到 `微信开发者工具`  
### 4.在`projiect.config.json`修改`appid`为你自己的  
### 5.在`app.js`里找到最上面几行，将云环境`id`（`env`那里）改成你自己的  
### 6.打开`云开发`，分别配置`云数据库`和`云存储`，参考下图  
  
#### 云数据库
  
![Image text](https://raw.githubusercontent.com/547414/tkwxxcx/master/remade/2.png)
  
#### 云存储
  
![Image text](https://raw.githubusercontent.com/547414/tkwxxcx/master/remade/1.png)
  
### 7.在`app.js`里按`Ctrl+F`调出搜索框搜索  
`db.collection('message').doc("6b81e0b4-e39f-47a1-bc7c-b604ffb2914e").get().then(res => {`  
然后将doc("`6b81e0b4-e39f-47a1-bc7c-b604ffb2914e`")中双引号引起开的换成你自己配置的  
  
### 8.将`云开发`中的 `云数据库` 中的 `file_id` 改成 `云存储`中你上传的文件的`File ID`  
  
### 9.云数据库数据项说明：  
`字段`-------------`示例值`---------`说明`  
`file_id`---------`cloud://...`---`自带题库文件（上传到云存储的文件）的文件ID`  
`message`---------`欢迎使用`-------`小程序首页中间偏下面显示的消息（更改后重新加载首页（或重启小程序）即可刷新）`  
`update_data`----`1`---------------`自带题库数据更新标记，更新时，需要将此字段值加1，比如由1变为2（只能加，不能少）`  
`update_version`-`1.0.0`----------`数据刷新标记，当要清空所有用户本地数据（缓存）时，更改此值（不同即可，建议加1）`  
****
## 七、自定义题库模块说明【注意】
这个需要服务器  
然后在`zzs.js`中找到  
`url: "https://crysu.com/zhddktk/upload/" + id + ".txt",`  
这行，将url换成你自己的  
另外，还需要自行在服务器中配置服务器网页端服务
****
## 八、服务器网页端说明
将服务器网页端文件夹改成英文名放入你的服务器中，并配置好`php+nigix/apache`环境即可  
在小程序后台`（微信公众平台）配置域名（需要ICP备案）`  
****
## 九、自定义题库题目格式说明
1  
单选题  
山西太原县清代举人刘大鹏（1857—1943年）所著的《退想斋日记》记载：“倭夷入寇，我军征剿不力，望风溃退，爵相一意立和。”反映的历史事件是（）  
A：鸦片战争  
B：第二次鸦片战争  
C：中日甲午战争  
D：八国联军侵华  
$#  
$#  
$#  
c  
2  
判断题  
王明“左”倾冒险主义的使党在白区的革命力量几乎损失了100%。  
A:正确  
B:错误  
$#  
$#  
$#  
$#  
$#  
a  
3  
多选题  
在中国共产党产生以后,中国社会存在的三种主要建国方案是  
A:地主阶级与买办性的大资产阶级的方案  
B:农民阶级的方案  
C:民族资产阶级的方案                 
D:工人阶级和其他进步势力的方案  
E:城市小资产阶级的方案  
$#  
$#  
acd  
如上，如果当前选项没有，用`$#`代替  
文件为txt文件  
文档最前面最后面不要有多余的东西，包括空格  
每道题有11行  
答案必须是小写的  
#### 1.自定义题库示例文件
https://github.com/547414/tkwxxcx/tree/master/remade/data.txt  
#### 2.题库格式帮助视频
https://github.com/547414/tkwxxcx/tree/master/服务器网页端/img/help.mp4  
或：  
https://crysu.com/zhddktk/img/help.mp4  

#### 3.题库格式Excel示例
https://github.com/547414/tkwxxcx/tree/master/服务器网页端/img/《马克思主义基本原理》机考题库---20190401.xls
  
****
## 十、自带题库格式说明
#### 每道题的格式和自定义题库一样
使用 `/%*/` 分割四个题库，默认顺序是近代史、思修、马原、毛概  
必须有四个题库，也就是四个分隔符，即使是每个题库里只有一道题，如果多了用不到，可以改`zds.wxml`把多余的题库进口按钮删了  
#### 1.自带题库示例文件
https://github.com/547414/tkwxxcx/tree/master/remade/data2.txt  
****
## 十一、关于遇到的问题
#### 1.自带题库题目加载不出来
在题库文件（data.txt）没问题的情况下，尝试修改 `数据库的权限`  
  
![Image text](https://raw.githubusercontent.com/547414/tkwxxcx/master/remade/3.png)
#### 2.换行符问题
使用WPS编辑的话有可能导致换行符不标准的问题。
换行符是隐匿的，一般看不到的。可使用`notepad++`，勾选 `视图`-`显示符号`-`显示所有字符` 然后查看换行符是否如图所示。  
如果不是，则可以将其复制进excel里，再复制出来。  
  
![Image text](https://raw.githubusercontent.com/547414/tkwxxcx/master/remade/4.png)
#### 3.如何去除导入题库模块
在`app.json`里删除如图高亮选中部分  
  
![Image text](https://raw.githubusercontent.com/547414/tkwxxcx/master/remade/5.png)
#### 4.如何删除广告位 
因为小程序增加广告位是有用户数量要求的，如果你要上线，要删除项目里的广告位（在`index.wxml`里），如果满足了要求，想要增加广告位，也请修改图中的内容。  
  
![Image text](https://raw.githubusercontent.com/547414/tkwxxcx/master/remade/6.png)    
#### 5.导入题库后乱码
编码格式问题，改题库文件编码格式为`utf-8`，还不行的话，再改成`ansi`  
  
![Image text](https://raw.githubusercontent.com/547414/tkwxxcx/master/remade/7.png)  
#### 6.如何快速锁定题库文件错误位置
拿自定义题库举例，当题库文件格式不对时，小程序端导入题库后往往会啥都不显示。  
此时，可以用二分法快速锁定错误位置。  
  
何为二分法：例如一组排好序的数字序列，如：  
`第几位数：0--1--2--3--4---5---6---7---8`  
 `----数字：25,36,47,89,120,520,521,666,888`  
当我们想要找到`520`这个数字时，我们可以先找第`（0+8）/2`（取整）的位置的数字，就是第`4`位（从0开始数），即`120`，发现`520`比`120`大，那么往后找，即`（5+7）/2`的位置，即第`6`位，是`521`，以此类推，直到找到`520`为止。  
  
所以这里的话，我们知道每道题有`11`行，比如有`88`道题，那么我们先找`88/2=44`的位置的题，把鼠标光标放在这道题的最后一行上，看看行数，如果`除以11`，余数`不是0`的话，那么这道题前面有问题，`是0`的话，后面有问题，以此类推，直到找到为止。  
  
![Image text](https://raw.githubusercontent.com/547414/tkwxxcx/master/remade/8.png) 
****
## 关于
个人网站：https://crysu.com/  
  
支持一下： 
  
微信  
![Image text](https://crysu.com/wp-content/uploads/2020/11/2020110505351554.png)
  
支付宝  
![Image text](https://crysu.com/wp-content/uploads/2020/11/2020110505351635.png)
  
****
