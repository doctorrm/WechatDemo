#后台系统管理

* 边做边设计库表。
* 把ssm框架搭好。
* 首页新闻管理:
管理员登录后，点击新闻管理模块，将会列出所有的新闻，管理员可以添加(编辑)、删除、修改新闻，选择特定几个新闻发布在前端。
* 管理员的登陆与退出登录(特定用户名和特定密码)
* 商品的管理模块，增删改查（solr）。

***
#前端（比较多）

* 首页的商品显示和新闻轮播（留出查询接口）。

* 商品详情页面包含轮播

* 购物车:
点击商品后加入商品详情页面，点击添加到购物车可以添加到购物车。
然后，点击购物车按钮后跳转到购物车界面，列出所有添加到这里的商品。


* 用户验证:
关于登录方面不打算做，系统假设的是单一商家，所以只需要姓名，手机号（含验证码），收货地址就可以了。（跟在微信跟人买东西一样）
但是客户下次登陆如何判断是那个客户呢？根据公众号！！！
我关注了公众号，就会有一个序列在后台，关注者姓名地址什么的都是和关注者独立的序号来一起放在数据库中的。
* 商品查询:
计划用solr&lucene。点击查询图标，会根据填写的查询条件查询，然后列出所有符合条件的商品。

* 订单查询:
分为5个子模块:
全部(所以历史购买的东西，包括待付款)、
待付款（点击付款按钮之后没有继续付款的）、
待发货(付了款但是商家没有在后台点击发货的)、
待收获(商家点击了发货但是用户没有点击确认收货的)、
待评价（用户点击了确认收货但是没有点击评价的）。

*  

***
#补充要做的事情，很重要的
* 前端：改进图片上传的顺序要求，做到可以直接在网页以可视化的方式对图片进行排序。
* 后台：检索商品功能。
* 后台：上传多张图片中，需要验证上传图片的名字是否为数字，如果是数字还要在int类型的限制范围内，因为后台获取后会把这个数字存入int类型的变量中中！很重要，这个！
* 后台：刷新界面过于频繁就会导致前端ajax不知道什么原因而发送不了。
* 后台：虽然可能会很麻烦，但后面还是要把整型的价格改为浮点型。

***
# 系统设计(设计理念问题,牵一发而动全身的特征,避免轻易改)
* 保存到磁盘的封面图片命名为main.jpg,是存放在以商品名字为名字的文件夹中的,文件夹包括方面图片还有其它的图片。
* html的id和class等前端和后台都是有小小的规范的。不记得就看已经写过的!
* 每修改一处比较大的地方必须进行验证，而且要至少2个浏览器上看看兼容性(推荐chrome和firefox)
*
