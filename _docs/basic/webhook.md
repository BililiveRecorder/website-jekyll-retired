---
title: Webhook
---

### Webhook V2

Webhook V2 会在录制开始、文件打开、文件关闭、录制结束时向填写的地址发送 HTTP POST 请求

请注意录播姬不保证各个事件的发送、接收到的顺序。

不保证发送顺序举例：  
`SessionEnded` 的 `EventTimestamp` 是 `2021-05-14T20:00:00.4960899+08:00`  
而 `FileClosed` 的 `EventTimestamp` 是 `2021-05-14T20:00:00.5071815+08:00`

不保证接收顺序举例：  
`SessionEnded` 可能会在 `FileClosed` 之前收到  
下一个文件的 `FileOpening` 有可能在上一个文件的 `FileClosed` 之前收到

如果返回的 HTTP 状态码不为 2xx 系列或请求出错，最多会尝试三次。重试时发送的所有数据均不变。

请求内容例：

```text
POST /path/to/url
Host: your.host.example.com
Content-Type: application/json
User-Agent: BililiveRecorder/1.3.1
```

```json
{
  "EventType": "SessionStarted",
  "EventTimestamp": "2021-05-14T17:52:44.4960899+08:00",
  "EventId": "e3e1c9ec-f386-4bc3-9e5a-661bf3ed2fb2",
  "EventData": {
    "SessionId": "7c7f3672-70ce-405a-aa12-886702ced6e5",
    "RoomId": 23058,
    "ShortId": 3,
    "Name": "3号直播间",
    "Title": "哔哩哔哩音悦台",
    "AreaNameParent": "生活",
    "AreaNameChild": "影音馆"
  }
}
```

```json
{
  "EventType": "FileOpening",
  "EventTimestamp": "2021-05-14T17:52:50.5256394+08:00",
  "EventId": "6e7b33e5-4695-4d25-87ee-b09f66e20ba0",
  "EventData": {
    "RelativePath": "23058-3号直播间/录制-23058-20210514-175250-哔哩哔哩音悦台.flv",
    "FileOpenTime": "2021-05-14T17:52:50.5246401+08:00",
    "SessionId": "7c7f3672-70ce-405a-aa12-886702ced6e5",
    "RoomId": 23058,
    "ShortId": 3,
    "Name": "3号直播间",
    "Title": "哔哩哔哩音悦台",
    "AreaNameParent": "生活",
    "AreaNameChild": "影音馆"
  }
}
```

```json
{
  "EventType": "FileClosed",
  "EventTimestamp": "2021-05-14T17:52:54.9461101+08:00",
  "EventId": "98f85267-e08c-4f15-ad9a-1fc463d42b0b",
  "EventData": {
    "RelativePath": "23058-3号直播间/录制-23058-20210514-175250-哔哩哔哩音悦台.flv",
    "FileSize": 816412,
    "Duration": 4.992,
    "FileOpenTime": "2021-05-14T17:52:50.5246401+08:00",
    "FileCloseTime": "2021-05-14T17:52:54.9461101+08:00",
    "SessionId": "7c7f3672-70ce-405a-aa12-886702ced6e5",
    "RoomId": 23058,
    "ShortId": 3,
    "Name": "3号直播间",
    "Title": "哔哩哔哩音悦台",
    "AreaNameParent": "生活",
    "AreaNameChild": "影音馆"
  }
}
```

```json
{
  "EventType": "SessionEnded",
  "EventTimestamp": "2021-05-14T17:52:54.9481095+08:00",
  "EventId": "e1f4a36e-e34c-4ada-80bb-f6cfc90e99e9",
  "EventData": {
    "SessionId": "7c7f3672-70ce-405a-aa12-886702ced6e5",
    "RoomId": 23058,
    "ShortId": 3,
    "Name": "3号直播间",
    "Title": "哔哩哔哩音悦台",
    "AreaNameParent": "生活",
    "AreaNameChild": "影音馆"
  }
}
```

### Webhook V1

Webhook V1 在每个文件结束时触发

请求内容例：

```text
POST /path/to/url
Host: your.host.example.com
Content-Type: application/json
User-Agent: BililiveRecorder/1.3.1
```

```json
{
  "EventRandomId": "bc2d0a41-2711-4f9b-8619-e54104fe90d8",
  "RoomId": 14846654,
  "Name": "小司无常",
  "Title": "【跨界冥神】打mua将！",
  "RelativePath": "14846654/record/20210107/150616.flv",
  "FileSize": 3749098123,
  "StartRecordTime": "2021-01-07T15:06:16.1387156+08:00",
  "EndRecordTime": "2021-01-07T16:06:16.1693244+08:00"
}
```

如果返回的 HTTP 状态码不为 2xx 系列或请求出错，最多会尝试三次。重试时发送的所有数据均不变。
