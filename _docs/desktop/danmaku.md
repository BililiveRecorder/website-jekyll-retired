---
title: 弹幕录制
---

录播姬支持在录制直播的同时保存直播弹幕。录制弹幕功能**默认为关闭**状态，需要在设置里启用。

除了弹幕以外，录播姬还支持保存

- SuperChat
- 礼物
- 上船
- 前三种消息和弹幕的原始数据

从 **v1.1.24** 开始，录播姬输出的 xml 添加了样式表，支持在浏览器中直接打开，效果如下。部分浏览器不支持此功能，会显示成一大堆纯文本。

![dm_1](/img/docs_dm_1.png)

![dm_2](/img/docs_dm_2.png)

弹幕的保存格式兼容 B站主站弹幕 XML 格式，可以使用**现有的 B站弹幕 XML 转 ASS 工具**进行处理，但是只能处理其中的弹幕信息。  
如果需要在视频中显示 SC、礼物、上传、等 其他信息，需要用户自行编写工具进行转换处理。

常见的 B站弹幕 XML 转 ASS 工具 （**以下所有工具、软件均与本项目无关**）

- <a href="https://github.com/hihkm/DanmakuFactory#%E8%8E%B7%E5%8F%96" rel="noopener noreferrer nofollow" target="_blank">DanmakuFactory<i class="fa fa-external-link" style="margin-left:5px"></i></a>
- <a href="https://tiansh.github.io/us-danmaku/bilibili/" rel="noopener noreferrer nofollow" target="_blank">bilibili ASS 弹幕在线转换<i class="fa fa-external-link" style="margin-left:5px"></i></a>

支持字幕的播放器 （**以下所有工具、软件均与本项目无关**）

- <a href="https://www.videolan.org/vlc/download-windows.html" rel="noopener noreferrer nofollow" target="_blank">VLC<i class="fa fa-external-link" style="margin-left:5px"></i></a>
- <a href="https://potplayer.daum.net/" rel="noopener noreferrer nofollow" target="_blank">PotPlayer<i class="fa fa-external-link" style="margin-left:5px"></i></a>
