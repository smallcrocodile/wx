#### 缘起  
想用 Python 开发一个微信公众号. 实现的需求是:   
> 用户向公众号发送视频, 视频被后台接收. 通过阿里云的视频转码服务进行压缩转码, 然后把转码好的视频发送回给用户.   

#### 已有经验

1. 之前用 PHP 写过微信公众号啦. 
2. 已经实现过了图片方向的你问我答.
3. 不知道视频类的会不会一样. 而且涉及后台, 琢磨着是不是要跟 OSS 相关呐. 

#### 不管了, 开干.

1. 先去阿里云买个 ECS 再说? 嗯哼.
2. [官文出了教程](https://mp.weixin.qq.com/wiki)
3. 是用 web.py 搞定的. 试一下?!
4. 先把之前的接口再用 python 从新跑通一遍, 确定我不是疯了.
5. 然后看看视频怎么搞.
6. 看看阿里后台视频怎么转码.
7. 齐活.

#### 以上是我的瞎琢磨...我先试试昂.

1. 买阿里云 ECS:  买了最便宜的版本. 耗时 40+ mins
原因: 以前自己的另一个网站 [马村的夏天](www.macundexiatian.com) 已经有一个 阿里云 了. 心想再放个公众号总归没问题吧. 然后上去鬼使神功的重装了一个 nginx, 有因为之前文件奇葩的 location... 我竟然把马村给玩炸了...玩炸了...内心受到极大惊吓. 而且发现 ECS 竟然没有开通快照. 回滚不了. T^T 哭泣的去找晓寅了...恢复之后, 自己默默另买了一个服务器. 
2. 
