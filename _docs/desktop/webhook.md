---
title: Webhook
---

从 v1.1.26 开始添加了 Webhook 功能，在每个文件写入完毕时触发。

请求内容例：

```http
POST /path/to/url
Host: your.host.example.com
Content-Type: application/json
User-Agent: BililiveRecorder/1.1.26.0-d37a3c29

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

如果返回的 HTTP 状态码不为 2xx 系列或请求出错，最多会尝试三次。重试时包括 `EventRandomId` 在内的所有值均不变。
