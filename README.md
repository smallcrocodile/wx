1. [Django+ Nginx + uWsgi 部署 (微信公众号开发一)](http://yixuan.li/geek/2017/02/16/Django/)
 * Version 0   : Feb.16, 2017
 * Version 0.1 : Feb 19, 2017 
2. [通过微信的 token (Django微信公众号开发二)](http://yixuan.li/geek/2017/02/19/wechatToken/)
 * Version 0   : Feb.19, 2017
3. [微信的接收与回复 (Django微信公众号开发三)](http://yixuan.li/geek/2017/02/20/wechatResp/)
 * Version 0: Feb 20, 2017 此处实力懵逼 ing, 

**注意**: 此刻代码没有任何 fork 及抄作业价值, 如果你已经过了 token 了 就不要浪费时间了. 如果还没有, 可以从第一篇文章开始抄作业. 谢谢大家.  

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
**原因**: 以前自己的另一个网站 [马村的夏天](www.macundexiatian.com) 已经有一个 阿里云 了. 心想再放个公众号总归没问题吧. 然后上去鬼使神功的重装了一个 nginx, 有因为之前文件奇葩的 location... 我竟然把马村给玩炸了...玩炸了...内心受到极大惊吓. 而且发现 ECS 竟然没有开通快照. 回滚不了. T^T 哭泣的去找晓寅了...恢复之后, 自己默默另买了一个服务器. 
2. 事后智慧之...  
  * 我就说个坑: ECS + Nginx 配置环境... token 无论如何过不去. 后来发现端口被占用了.    
   * 首先, 俺不知什么时候把 nginx 的 listen 全部注释掉了.  
   * Google 之, 发现加个 location, 把 nginx 反向代理一下就能过了.  
   * 具体反向代理不明, 总之是过了.  
   * But! 我靠, 个人的微信号是特么没有视频下载接口的. 所以还是要在无封印领域玩那.  
   * 于是弄测试号 ing... token 又不通了是也乎...  
   * 继续折腾哈...  
    
3. 换框架时候到了.
  * **Hell**: 反正已经拿 web.py 跑了一通, 官网的教程都 ok 了. 也完成了`发语音` → `识别语音` → `返回识别文字` 这个坑. 
  * 那么再拿 Django 试试?   
  
  [Feb. 13 19:56] : 明天情人节, 要出门和犬帮吃饭. 测试号 token 先过去啊! 同样的功能拿 Django 再玩一遍才是真好汉呐! BTW...白浅都跳完诛仙台了...表示错过了挖眼睛, 生孩子, 跳诛仙台...我很难受. 赶紧的搞定!
