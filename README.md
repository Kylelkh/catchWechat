# CatchWechat
抓取微信公众号文章

pre：
   没有用框架，直接clone 就可以用 
   
基于 python 2.7 。使用3的话，编码和print语法更换一下即可。


 - `catch_allList.py` ：  <a href="http://www.leon0204.com/wechat.html" target="_blank">推荐使用，抓取指定 公众号url (持续更新)</a>
 
 
 
 延伸：
 - `dailydown.py` ： <a href="http://www.leon0204.com/wechat.html" target="_blank">采集配置的公众号的文章效果</a>
 - `dailydownbyKeywords.py` ： <a target="_blank" href="http://www.leon0204.com/wechat.html">采集搜狗首页10个热点关键词，每日更新关键词对应的前10篇文章</a>   
 

####  安装 pip
```
wget --no-check-certificate https://github.com/pypa/pip/archive/1.5.5.tar.gz 
tar zvxf 1.5.5.tar.gz    
cd pip-1.5.5/
python setup.py install
pip install --upgrade pip
```

####  使用到的 pip 模块
```
pip install requests
pip install lxml
pip install BeautifulSoup

# Ubuntu
apt-get install libmysqld-dev
easy_install MySQL-python

# Centos
yum install python-devel
yum install mysql-devel

```


####  获取代码
```
cd /home/wwwroot
git clone https://github.com/leon0204/catchWecaht.git
```

#### 导入模板数据库，先创建 `weixin` 数据库 `utf8mb4`
```	
cd catchWecaht
mysql -uroot -p weixin < ./weixin.sql
```

>抓取公众号的列表在 `weixin` 数据库的 `subscription` 表中 


配置所需要用到的库，没有的用 `pip` 基本都可以满足



#### 抓取公众号今日更新列表
```
// 需要设置一下 dailydown.py 中的数据库设置
python dailydown.py
```
数据会存在 `subcatch` 表中 


#### 优化
1 资源删除，热点抓取bug 修复

`TODO` :
1. ~~dailyKeyword 采集热点关键词时，空数据时候插入，没数据是不会插入，没有写插入语句~~
2. ~~图片采集的优化 ~~
3. 添加TDK 

#### 更新 v1
1. 优化图片采集规则，更全面抓取图片 
2. 修复一些bug 

如果对你有帮助的话，帮忙右上角star一下，谢谢！
欢迎 PR ～

