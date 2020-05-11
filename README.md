# CrawlerFor98_2.1
​																											-----------制作人：abc2020

**这是一个自动收集98堂中文区信息的爬虫软件，并且我提供附加功能可以批量替换日文标题成为98堂的标题**

#### 一. 软件制作初衷

98的高清字幕一直是这里的特色，为了可以有效根据更多的关键词进行搜索，或者更快的浏览，所以在这里写一个可以进行**不断更新爬取**的软件，代替堂里其他人偶尔的更新

并且本人为了让我在选择电影时更有效的看到这是什么电影，特别根据爬取的数据为数据库写了可以自动替换日文标题的程序

**爬虫内容展示：**

![123](https://github.com/abcabc2020/abc_ImgRepo/blob/master/C3.png)

**文件更名软件结果展示：**

![125](https://github.com/abcabc2020/abc_ImgRepo/blob/master/C4.png)

#### 二. 软件功能说明&包含文件说明

##### 	1. CrawlerForS_x.x

对98堂**高清中文电影区有码部分**的数据进行爬取

###### 			1)CrawlerForS 软件功能：

a. 可以进行增量爬取，为了保证程序的效率，采用了日志的方法，即：./98_Data/result.txt文件记录了爬取的开始日期和结束日期,在这个基础上更新新的数据，简单快捷

b. 可以自动在爬取时下载对应的封面和截图（需要开代理，否则会出现大量失败），下载失败自动重试，如果失败自动记录在failimage.txt文件中

c. 新版增加多线程运行功能：可自定义线程数：图片下载线程，网页详细数据处理线程，每页url处理线程（有最大数量限制，超出自动变成最大数）

###### 	2）软件配置说明

![Image text](https://github.com/abcabc2020/abc_ImgRepo/blob/master/config1.png)

**a. 数据存放文件夹：**存放爬虫数据以及配置数据的文件夹，如果不存在会根据配置文件里的信息自动生成，如果没有什么特殊需要请不要乱动

**b. 线程数：**

​	图片下载线程：_下载图片的线程

​	目录爬取线程：爬取每一页url链接的线程，不用太多

​	爬虫线程：处理每一页数据的线程，可以稍微多一些，最多20个

**c. 爬取设置：**

​	开始页面：爬虫开始爬取的页面，一般就是第一页

​	结束页面：爬虫结束的页面，如果增量更新一般来说增量不会超过10页（除非你一个多月没更新），需要你设置的超过之前的最新数据所在的页面，程序到达上一次数据之后会停止

​	是否下载图片：本项目中图片没有下载完全，如果你有代理并且流量充足可以填写：是。PS.在之后的功能中会考虑添加单独下载图片的部分

​	是否增量下载：是否考虑上一次爬取的日期，建议打开，如果不打开会出现重复爬取，我增加这个选项完全是在我当初收集全项目时一段一段爬而设置的，而且在日志部分不考虑增量下载还有一些bug没有来得及处理

​	是否是第一次使用：如果填写是：在写入数据的时候会先写一行列索引进去，一般填否

**d. 98最新网址：**进入98论坛首页的网址

###### 	3）软件现有的bug

a. 反向的增量更新没有解决，不过这个项目现有的数据已经覆盖到了最后一页的数据

b. 如果不考虑增量更新

如果在使用过程中还有别的问题欢迎和我反映，邮箱：3440684287@qq.com

###### 	4) 附加文件说明

a. **initial_config.exe**重新生成**CrawlerForS**的配置文件，不过最新版中如果配置文件缺失是会自动生成的，生成后需要再次运行一下软件

b. **config.ini**是**CrawlerForS**的配置文件

##### 2. TitleReplace_x.x

对所选文件夹下的电影进行文件名替换，替换为98的汉语标题，影片的内容了解一大半，方便选择

###### 	1）软件功能：

a. 根据爬虫收集到的数据对所选文件名称进行替换（包括子文件夹）

b. 可以选择将上一级文件夹名称也一并替换，这个适用于使用emby等软件的用户

c. 同时可以修改nfo文件中的标题

d. 支持多文件夹处理

e. 支持识别-c，-C，㊥，三种中文形式，如果在数据库中找到了对应的数据（即该电影有中文字幕）那么会在文件名中写明“非中文”字样方便后续下载替换

待续.......



**根目录包含文件展示：**

![111](https://github.com/abcabc2020/abc_ImgRepo/blob/master/C2.png)

#### 三.软件下载

点击***clone***或者***downloadzip***按钮下载

数据会存储到./98_Data/Csv_data/98CTest.csv数据里面，查看时可以使用Excel打开

如果只想要数据也可以，**本项目是长期有效实时更新**，如果未能及时更新可以自行下载下来点击CrawlerForS_x.x.exe程序进行更新

配合更名软件可以替换影片日文名称，方便选择
