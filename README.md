# 题库微信小程序
注：切勿将 服务器网页端 文件夹放入 微信开发者工具，使用的时候注意分开，除了这个文件夹，其他的都可以放入微信开发者工具

微信题库小程序升级版

哔哩哔哩教程：https://www.bilibili.com/video/BV1zf4y1S7oF

导入自定义题库网址：https://crysu.com/zhddktk/

导入自定义题库网页源码，链接：https://pan.baidu.com/s/1d9v_58awrf-rBOM9OiOtZg 

提取码：nqjl

小程序端配置步骤  
1.下载本项目（master）  
2.删除master中的 服务器网页端 文件夹  
3.将项目（master）导入到 微信开发者工具  
4.在projiect.config.json修改appid为你自己的  
5.在app.js里找到最上面几行，将云环境id（env那里）改成你自己的  
6.打开云开发，分别配置云数据库和云存储，参考下图  
  
云数据库
![Image text](https://raw.githubusercontent.com/547414/tkwxxcx/master/remade/2.png)
  
云存储
![Image text](https://raw.githubusercontent.com/547414/tkwxxcx/master/remade/1.png)
  
7.在app.js里按Ctrl+F调出搜索框搜索  
db.collection('message').doc("6b81e0b4-e39f-47a1-bc7c-b604ffb2914e").get().then(res => {  
然后将doc("6b81e0b4-e39f-47a1-bc7c-b604ffb2914e")中双引号引起开的换成你自己配置的  
  
8.将云环境中的 云数据库 中的 file_id 改成 云存储你上传的文件的File ID  
  
9.云数据库数据项说明：  
字段···········示例值········说明  
file_id········"cloud://..."·自带题库文件（上传到云存储的文件）的文件ID  
message········欢迎使用······小程序首页中间偏下面显示的消息（更改后重新加载首页（或重启小程序）即可刷新）  
update_data····1·············自带题库数据更新标记，如果要更新自带题库数据，需要将此字段值加1，比如由1变为2（只能增加，不能减少）  
update_version·1.0.0·········数据刷新标记，当需要清空所有用户本地数据（缓存）时，将此值更改（不同即可，建议加1，否则次数多了可能出bug）  

