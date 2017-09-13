# flowplayer
flowplayer 一款免费的WEB视频播放器

Flowplayer 是一个开源（GPL 3的）WEB视频播放器。您可以将该播放器嵌入您的网页中，如果您是开发人员，您还可以自由定制和配置播放器相关参数以达到您要的播放效果。本文主要介绍Flowplayer的使用。

Flowplayer支持播放flv、swf等流媒体以及图片文件，能够非常流畅的播放视频文件，支持自定义配置和扩展。

1、加载flowplayer.js

在要播放视频的页面的head之间加入flowplayer.js。

<script type="text/javascript" src="js/flowplayer-3.2.6.min.js"></script> 
您可以到flowplyer官网上下载最新版本：http://flowplayer.org/download/index.html

2、XHTML

在需要加入播放器的地方加入如下一段代码：

<a href="flowplayer.flv" style="display:block;width:520px;height:330px" id="player"></a>  
将a标签的href属性指向要播放的视频地址，然后设置样式，宽度和高度，以及设置display:block，当然关键的是还要给a标签指定一个id，以便于JS调用。

当然你也可以只在html中指定一个DIV，然后由Javascript来控制播放地址，如：

<div id="player2" style="width:520px; height:330px"> </div>  
3、Javascript

在页面底部计入javascript脚本调用播放器：

<script type="text/javascript"> 
flowplayer("player", "flowplayer-3.2.7.swf"); 
</script> 
使用flowplayer()函数调用播放器，第一个参数是播放器的id，第二个参数是播放器的路径，它是一个flash文件，一定要保证播放器的路径正确。

如果不是使用a标签调用视频文件，而是使用DIV来调用，则代码如下：

flowplayer( 
    "player2",  
    "flowplayer-3.2.7.swf",{ 
      clip: { 
        url: "flowplayer.flv", 
        autoPlay: false,  
        autoBuffering: true  
      } 
    } 
); 
flowplayer()函数的第三个参数是可以进行多项设置的，其实就是高级设置。clip方法里的url：表示视频文件的真实地 址，autoPlay：表示是否自动播放，默认是true，autoBuffering：表示是否自动缓冲，即当视频文件设置为不自动播放时，播放器仍然 预先下载视频文件内容。

flowplayer还支持播放列表，以及皮肤设置等多项高级设置，具体设置方法，感兴趣的同学可以请访问：http://flowplayer.org/documentation/configuration/index.html。
