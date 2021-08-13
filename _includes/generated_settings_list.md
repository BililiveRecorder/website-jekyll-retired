## 目录

- [房间号](#房间号)
- [自动录制](#自动录制)
- [录制模式](#录制模式)
- [自动分段模式](#自动分段模式)
- [自动分段数值](#自动分段数值)
- [弹幕录制](#弹幕录制)
- [弹幕录制-原始数据](#弹幕录制-原始数据)
- [弹幕录制-SuperChat](#弹幕录制-SuperChat)
- [弹幕录制-礼物](#弹幕录制-礼物)
- [弹幕录制-上船](#弹幕录制-上船)
- [直播画质](#直播画质)
- [录制文件名格式](#录制文件名格式)
- [WebhookV1](#WebhookV1)
- [WebhookV2](#WebhookV2)
- [在界面显示标题和分区](#在界面显示标题和分区)

### 房间号

键名: `RoomId`  
类型: `int`  
默认设置: `default`



### 自动录制

键名: `AutoRecord`  
类型: `bool`  
默认设置: `default`



### 录制模式

键名: `RecordMode`  
类型: `RecordMode`  
默认设置: `RecordMode.Standard`



### 自动分段模式

键名: `CuttingMode`  
类型: `CuttingMode`  
默认设置: `CuttingMode.Disabled`



### 自动分段数值

键名: `CuttingNumber`  
类型: `uint`  
默认设置: `100`

按时长分段时为分钟，按大小分段时为MiB

### 弹幕录制

键名: `RecordDanmaku`  
类型: `bool`  
默认设置: `false`



### 弹幕录制-原始数据

键名: `RecordDanmakuRaw`  
类型: `bool`  
默认设置: `false`



### 弹幕录制-SuperChat

键名: `RecordDanmakuSuperChat`  
类型: `bool`  
默认设置: `true`



### 弹幕录制-礼物

键名: `RecordDanmakuGift`  
类型: `bool`  
默认设置: `false`



### 弹幕录制-上船

键名: `RecordDanmakuGuard`  
类型: `bool`  
默认设置: `true`



### 直播画质

键名: `RecordingQuality`  
类型: `string`  
默认设置: `10000`

录制的直播画质 qn 值，逗号分割，靠前的优先

### 录制文件名格式

键名: `RecordFilenameFormat`  
类型: `string`  
默认设置: `@"{roomid}-{name}/录制-{roomid}-{date}-{time}-{ms}-{title}.flv"`



### WebhookV1

键名: `WebHookUrls`  
类型: `string`  
默认设置: `string.Empty`



### WebhookV2

键名: `WebHookUrlsV2`  
类型: `string`  
默认设置: `string.Empty`



### 在界面显示标题和分区

键名: `WpfShowTitleAndArea`  
类型: `bool`  
默认设置: `true`




