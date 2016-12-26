# 校招薪水 #

----------

###应用场景:一个offer数据爆料和展示的内部交流平台###
###想法初衷:就是简单提供一个校招签约之前可以匿名的offer数据交流以及分享平台，不在依赖于网上的比如看准网，知乎查找之类的，纯靠校友，页面简单粗暴，直接打分，按照可信度来对比区分各个待遇，以便签约时候的谈薪水了解等，至于侵权方面，平台仅供内部交流，希望大家理解###
###使用框架：前端jquery mobile+后端django###
###相应客户端下载链接：[http://www.ioffershow.com:8000/application/](http://www.ioffershow.com:8000/application/ "客户端下载链接")
----------

###技术速成方案：###
####jqm基础学习：半天时间，找个模板看看，简易的样式基本都比较好学，学习网址：[点此访问](http://www.runoob.com/jquerymobile/jquerymobile-tutorial.html "学习网址")
####django基础学习：这个看能力了，快的一两天，慢的一个星期左右，python的web框架，比较容易上手，我在这个项目中也就用了基础的东西，基本是下面这个教程的基础篇吧，学习网址：[点此访问](http://www.ziqiangxuetang.com/django/django-tutorial.html "学习网址")
####数据库基本学习：这里用了一下mysql，django默认是sqlite3，数据导入导出不方便，所以改成了mysql

######补充说明：整个项目只是实现了基本业务，前端不是很好看，并没有考虑太多反爬虫，高并发之类的问题，还希望感兴趣的朋友能够有兴趣交流一下，谢谢，有兴趣的朋友欢迎提供更新版本哈。


----------

###环境部署：###
#####前期准备:ubuntu服务器+mysql安装+apache服务器
#####步骤1：
    sudo easy-install pip
#####步骤2（初学者过滤掉这一步，以后也没体现）：
    sudo pip install virtualenv
    virtualenv website
    source website/bin/activate
#####步骤3：下载django版本，我这用的是1.7.3版本
    pip install Django==1.7.3
#####步骤4：下载了源码的可以略过这一步，创建django项目offershow以及创建工程salary
    django-admin.py startproject offershow
    cd offershow
    python manage.py startapp salary
#####步骤5：在源码的offershow路径下启动应用，我是在腾讯云上的，暂时没有部署apache或者ngnix，所以直接开启服务自己测试就好
    python manage.py makemigrations 
    python manage.py migrate
    python manage.py runserver 0.0.0.0:8000（这里是默认外网可以从8000端口访问）
#####步骤6：服务部署上线，赶得匆忙没有经过太多的复杂部署，直接采用了django框架自带的服务器，利用screen保持服务不断的手段（有点low），之后再去学习一下部署了，最近也忙着去找工作。这一步，建议大家自己测试的时候不用到这一步，不然还得去学习一下screen命令哈。
#####步骤7：使用自己服务器部署的时候，需要修改一下setting文件的数据库密码和名字，其中mysqldb安装会略麻烦，解决方案已经在在git文件夹里面。
#####备注：以上是一些初级的学习以及简单的部署，安全性和并发都依赖于框架，所以做的不是很好，大神请勿喷，也请不要乱去爬取数据，需要的话可以直接问我要，毕竟服务器和流量都是自费的，至于有什么别的问题或者比较厉害的大神愿意主动教我的，可以直接issue或者邮件反馈交流哈，abc_123@zju.edu.cn


----------

###最后，项目的初衷是为了交流互助，薪水可能大家都了解了，为了响应最近朋友们对于代码和数据的需求，这小项目的代码都开源了，数据大概一个月以后在公布给大家，相对来说技术犹如界面和使用一样简单粗糙，适合初学者，但是意义还是有的，也很开心能够帮助到一些朋友。

----------
###前端朋友的福利：###
#####restful api接口文档已经更新，较之前版本改动有点大，分为测试版本跟上线版本，测试大家练手，上线请联系我，详情请查看在git里的数据文档信息中查找。
###上线版本的:
- 获取token信息接口
- 插入单条薪水信息接口
- 查单条薪水信息接口
- 查询所有薪水信息接口
- 薪水差评接口
- 薪水好评接口
- 获取薪水城市分类以及总数接口
- 获取薪水公司分类以及总数接口
- 获取薪水统计数据的接口
- 薪水数据查询的接口
- 薪水留言的接口
- 获取热门标签接口
- 提醒：使用前统一token访问限制，所有接口均改为post请求，访问数据或者请求，请附带access_token参数。

#####觉得页面丑陋，想自己写写练手的欢迎大家来参与，数据可以自行创建测试，如果可以的话，优秀的，我可以更新一下代码，展示你们的优秀版本，谢谢大家参与。

###数据的福利：###
#####数据已经公开，截至到10月30号为止已经有400多条数据，取之于众用之于众，如果大家需要，都可以取走，但希望数据使用的时候请转载出处，即此项目信息。数据仅限内部交流，请不要去大型网站论坛公开，如有侵权问题，后果自行承担。
#####数据文件已经更新在git项目的数据文档信息中，offerinfo.csv(这个可以用excel直接打开) offferinfo.json(后台数据交互的)


###项目进度与发展：###
#####数据已经公开，截至到10月30号为止已经有400多条数据，取之于众用之于众，如果大家需要，都可以取走，但希望数据使用的时候请转载出处，即此项目信息。数据仅限内部交流，请不要去大型网站论坛公开，如有侵权问题，后果自行承担。
#####数据文件已经更新在git项目的数据文档信息中，offerinfo.csv(这个可以用excel直接打开) offferinfo.json(后台数据交互的)
- 10.27 16:36更新 上线了一个小半天，目前已经有60条数据，200多点评了，比较开心，至少还是能够提供小部分帮助，希望大家真诚的填写，谢谢。
- 10.27 23:36更新 刚出门听了宣讲会，回来一看，已经有234条数据，1392条点评了，瞬间觉得这次貌似做了一个有意义的事情（喜欢许三多哈），于是乎，今晚决定加班好好改改。
- 10.28 04:16更新 数据量已经更新到249条，点评数据有了1521条了，关键是offer详情的浏览量累计已经突破了15W，鸡血满满，跟一个会前端的师弟沟通完，决定熬夜写完restful的接口，这样前端后端分离，顺便改进了几个需求。
- 10.29 17:04更新 数据量334条，点评数据有了2500条了，累计offer详情页面访问量超过了26w（貌似排行榜第一个有问题，后台数据我没有动过，应该是有人爬取吧，希望这样的人放过我，要数据，去git上有的，不过排除一下也是超过了20w），比较开心，今天顺便周六，白天木有出去玩，安安静静的在宿舍写完了一些关于代码开源以及数据的东西，写的还比较详细，希望感兴趣的朋友可以去加入，如果厉害的朋友指点一下我那就更好。
- 11.01 11:00更新 数据量433条，点评数据有了3399条了，累计offer详情页面访问量超过了45w，虽然根据后台ip访问看到有部分数据是有人爬取的，但433跟3399的数据，我相信绝大多数都是每一个人认真贡献的，在此也非常感谢无私的各位，其实用计算机的一个概念来说，这也是众包，是大家一起协作的成果，所以本着共享原则，数据决定公开了，个人也花了一天时间去学习django+uwsgi+nginx的部署，近期就可以改进一下，接口也直接增加了关于数据统计，查询分类的一些接口。后台数据也已经公开，希望有需要的人可以共享，但希望大家能够转载一下出处即git项目信息地址。
- 11.01 15:00更新 利用白天写的接口更新了一下页面，修改一些bug，主要是提供了关键字搜索功能，匹配公司名，工作地，岗位等。
- 11.03 18:00更新 offer数据信息已经有了537条，点评数据达到了4073，详情页面访问量累计51w，关键字搜索词数达到了4000多条，且已经有朋友更新了android版本，准备在正式的代码服务器上添加token访问令牌，以便使用，具体的这周末应该就能更新。
- 11.07 17:00更新 数据量579条，点评数据有了4592条了，累计访问量56w，墨迹了一个星期，数据增长比较缓慢，更新了返回按钮问题，然后更改了页面显示不全的问题，提供了留言接口，目前已经有两个安卓端了，我已经写好了正式上线版（带令牌的）接口数据，需要的情去git看文档。谢谢大家的关注，git已经有31个star了，虽然拖了一会，但还是会在能力范围内继续更新。
- 11.08 17:00更新 鉴于页面加载速度太慢，更新了一下页面，大家直接使用搜索功能而不是直接所有数据展示，暂时没做分页，这样减少一点流量。同时添加修改了留言接口。
- 11.15 17:00更新 数据量669条，点评数据有了5314条了，累计访问量63w，android版本已经更新两个版本，欢迎大家使用。
- 11.18 02:00更新 android版本已经更新两个版本，IOS开始内测，并且参考安卓版本的意见，提供了详情页面的标签搜索，且未了减少大家使用数据流量，最新最热最信只提供了前100名，提倡大家使用搜索功能。增加了热门标签获取的接口，代码暂时不更新了，先去实现了功能再来更新
- 11.21 01:00更新 历时2天，写完了这个笑招社区的小模块，灵感来自于热心网友建议，希望大家能够喜欢，求职之余能够给大家带来欢乐！暂时上线网页版
- 11.24 19:00更新 上线IOS版本
###近期计划：###
#####1.django+uwsgi+nginx的部署方案暂时不会提供，很多用户记住了8000端口。。。
#####2.根据使用情况提供一个类似于众包的机制，鼓励大家来完善信用度为10以上的offer信息，更加详细的展示这些数据，比如公积金，签字费，月到手收入等等。目前采用留言替代了。
#####3.很想需要几个热心朋友来帮忙实现一个薪资的小小的语义库，不知道有没有人愿意寒假来实现呀。代码因为毕设问题很少更新了。
#####4.重要的事情说三遍！有问题群里交流咯，请不要去爬数据，要数据群里找我，要接口群里找我，有bug群里找我
###offershow交流反馈QQ群:371473277
###offershow交流反馈QQ群:371473277
###offershow交流反馈QQ群:371473277


