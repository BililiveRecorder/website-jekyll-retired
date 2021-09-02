---
title: 弹幕录制
redirect_from:
  - /docs/desktop/danmaku
  - /docs/desktop/danmaku/
---

录播姬支持在录制直播的同时保存直播弹幕。  
录制弹幕功能**默认为关闭**状态，可以在全局设置或直播间单独设置里启用。

除了弹幕以外，录播姬还支持保存

- SuperChat
- 赠送礼物
- 舰长购买
- 前三种消息和弹幕的原始数据

弹幕的保存格式兼容 B站主站弹幕 XML 格式，可以使用现有的弹幕格式转换工具进行处理。

大部分转换工具只能读取录播姬弹幕XML里的普通弹幕。  
DanmakuFactory 从 v1.6x 开始支持转换录播姬的 礼物、舰长购买、SuperChat 数据。

把弹幕XML转换为ASS字幕之后就可以在支持ASS字幕的视频播放器里加载查看了。

[推荐配合使用的转换工具、视频播放器](/docs/basic/related/)

录播姬输出的 XML 含有样式表，支持在浏览器中直接打开，效果类似下图。  
部分浏览器（如 IE）不支持此功能，会显示成一大堆纯文本，建议使用较新版本的 Chrome Edge Firefox 等浏览器。

![dm_1](/img/docs_dm_1.png)

![dm_2](/img/docs_dm_2.png)
