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

设为 `true` 为启用自动录制，`false` 为不自动录制。

### 录制模式

键名: `RecordMode`  
类型: `RecordMode`  
默认设置: `RecordMode.Standard`

本设置项是一个 enum，键值对应如下：

| 键 | 值 |
|:--:|:--:|
| RecordMode.Standard | 0 |
| RecordMode.RawData | 1 |

关于录制模式的说明见 [录制模式](/docs/basic/record_mode/)

### 自动分段模式

键名: `CuttingMode`  
类型: `CuttingMode`  
默认设置: `CuttingMode.Disabled`

本设置项是一个 enum，键值对应如下：

| 键 | 值 |
|:--:|:--:|
| CuttingMode.Disabled | 0 |
| CuttingMode.ByTime | 1 |
| CuttingMode.BySize | 2 |

### 自动分段数值

键名: `CuttingNumber`  
类型: `uint`  
默认设置: `100`

根据 CuttingMode 设置的不同：    
当按时长分段时，本设置的单位为分钟。  
当按大小分段时，本设置的单位为MiB。

### 弹幕录制

键名: `RecordDanmaku`  
类型: `bool`  
默认设置: `false`

是否录制弹幕，`true` 为录制，`false` 为不录制。

本设置同时是所有“弹幕录制”的总开关，当本设置为 `false` 时其他所有“弹幕录制”设置无效，不会写入弹幕XML文件。

### 弹幕录制-原始数据

键名: `RecordDanmakuRaw`  
类型: `bool`  
默认设置: `false`

是否记录原始 JSON 数据。

弹幕原始数据会保存到 XML 文件每一条弹幕数据的 `raw` attribute 上。

当 `RecordDanmaku` 为 `false` 时本项设置无效。

### 弹幕录制-SuperChat

键名: `RecordDanmakuSuperChat`  
类型: `bool`  
默认设置: `true`

是否记录 SuperChat。

当 `RecordDanmaku` 为 `false` 时本项设置无效。

### 弹幕录制-礼物

键名: `RecordDanmakuGift`  
类型: `bool`  
默认设置: `false`

是否记录礼物。

当 `RecordDanmaku` 为 `false` 时本项设置无效。

### 弹幕录制-上船

键名: `RecordDanmakuGuard`  
类型: `bool`  
默认设置: `true`

是否记录上船（购买舰长）。

当 `RecordDanmaku` 为 `false` 时本项设置无效。

### 直播画质

键名: `RecordingQuality`  
类型: `string`  
默认设置: `10000`

录制的直播画质 qn 值，以英文逗号分割，靠前的优先。

**注意**（从录播姬 1.3.10 开始）：

- 所有主播刚开播时都是只有“原画”的，如果选择不录原画会导致直播开头漏录。
- 如果设置的录制画质里没有原画，但是主播只有原画画质，会导致不能录制直播。
- 录播姬不会为了切换录制的画质主动断开录制。

画质 | qn 值
:--:|:--:
4K | 20000
原画 | 10000
蓝光(杜比) | 401
蓝光 | 400
超清 | 250
高清 | 150
流畅 | 80

### 录制文件名格式

键名: `RecordFilenameFormat`  
类型: `string`  
默认设置: `@"{roomid}-{name}/录制-{roomid}-{date}-{time}-{ms}-{title}.flv"`

- 只支持 FLV 格式
- 所有大括号均为英文半角括号
- 录制时如果出现文件名冲突，会使用一个默认文件名

变量 | 含义
:--:|:--:
{date} | 当前日期（年月日）
{time} | 当前时间（时分秒）
{ms} | 当前时间毫秒
{roomid} | 房间号
{title} | 标题
{name} | 主播名
{parea} | 大分区
{area} | 子分区
{random} | 随机数字


### WebhookV1

键名: `WebHookUrls`  
类型: `string`  
默认设置: `string.Empty`

具体文档见 [Webhook](/docs/basic/webhook/)

### WebhookV2

键名: `WebHookUrlsV2`  
类型: `string`  
默认设置: `string.Empty`

具体文档见 [Webhook](/docs/basic/webhook/)

### 在界面显示标题和分区

键名: `WpfShowTitleAndArea`  
类型: `bool`  
默认设置: `true`

只在桌面版（WPF版）有效


## 高级设置

<span style="color:red">重要说明</span>：一般用户通常不需要也不应该修改高级设置。  
对各个 Timing 的修改可能会导致被B站服务器屏蔽、不能及时开始录制等问题。

显示高级设置的方法：右键双击界面左下角的设置按钮

### 请求 API 时使用的 Cookie

键名: `Cookie`  
类型: `string`  
默认设置: `（空字符串）`



### 请求的 API Host

键名: `LiveApiHost`  
类型: `string`  
默认设置: `"https://api.live.bilibili.com"`



### HTTP API 检查时间间隔 秒

键名: `TimingCheckInterval`  
类型: `uint`  
默认设置: `600 (10分)`



### 录制断开重连时间间隔 毫秒

键名: `TimingStreamRetry`  
类型: `uint`  
默认设置: `6000 (6秒)`



### 录制无指定画质重连时间间隔 秒

键名: `TimingStreamRetryNoQn`  
类型: `uint`  
默认设置: `90 (1.5分钟)`



### 连接直播服务器超时时间 毫秒

键名: `TimingStreamConnect`  
类型: `uint`  
默认设置: `5000 (5秒)`



### 弹幕服务器重连时间间隔 毫秒

键名: `TimingDanmakuRetry`  
类型: `uint`  
默认设置: `9000 (9秒)`



### 最大允许未收到直播数据时间 毫秒

键名: `TimingWatchdogTimeout`  
类型: `uint`  
默认设置: `10000 (10秒)`



### 触发刷新弹幕写入缓冲的个数

键名: `RecordDanmakuFlushInterval`  
类型: `uint`  
默认设置: `20`


