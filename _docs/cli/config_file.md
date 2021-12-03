---
title: 配置文件
---

所有版本的录播姬（桌面版、命令行版）的配置文件格式都完全一样并且通用。  
配置文件是工作目录里的 `config.json` 文件。

如果需要手动修改配置文件，推荐使用的编辑器是 VSCode。  
推荐添加 JSON Schema，会有自动补全和简单设置说明。

关于所有设置项的列表可以参考 [软件设置](/docs/basic/settings/)

现在录播姬配置文件的版本号是 2

```json
{
  "$schema":"https://raw.githubusercontent.com/Bililive/BililiveRecorder/dev-1.3/configV2.schema.json",
  "version": 2,
  "global": {},
  "rooms": []
}
```

录播姬的设置是层级结构的，如果单房间没有设置就会使用全局设置，如果全局没有设置就会使用默认设置。每个配置项都是下面这样的结构：

```json
{
  "HasValue": true,
  "Value": "value"
}
```

`HasValue` 为 `true` 时使用此处设置的值，为 `false` 时使用更高一层的设置。

配置文件内容示例：

```json
{
  "version": 2,
  "global": {
    "TimingStreamRetry": {
      "HasValue": false,
      "Value": 0
    },
    "TimingStreamConnect": {
      "HasValue": false,
      "Value": 0
    },
    "TimingDanmakuRetry": {
      "HasValue": false,
      "Value": 0
    },
    "TimingCheckInterval": {
      "HasValue": false,
      "Value": 0
    },
    "TimingWatchdogTimeout": {
      "HasValue": false,
      "Value": 0
    },
    "RecordDanmakuFlushInterval": {
      "HasValue": false,
      "Value": 0
    },
    "Cookie": {
      "HasValue": false,
      "Value": null
    },
    "WebHookUrls": {
      "HasValue": false,
      "Value": null
    },
    "WebHookUrlsV2": {
      "HasValue": false,
      "Value": null
    },
    "LiveApiHost": {
      "HasValue": false,
      "Value": null
    },
    "RecordFilenameFormat": {
      "HasValue": false,
      "Value": null
    },
    "WpfShowTitleAndArea": {
      "HasValue": true,
      "Value": true
    },
    "RecordMode": {
      "HasValue": false,
      "Value": 0
    },
    "CuttingMode": {
      "HasValue": true,
      "Value": 1
    },
    "CuttingNumber": {
      "HasValue": false,
      "Value": 0
    },
    "RecordDanmaku": {
      "HasValue": true,
      "Value": true
    },
    "RecordDanmakuRaw": {
      "HasValue": false,
      "Value": false
    },
    "RecordDanmakuSuperChat": {
      "HasValue": true,
      "Value": false
    },
    "RecordDanmakuGift": {
      "HasValue": true,
      "Value": false
    },
    "RecordDanmakuGuard": {
      "HasValue": true,
      "Value": false
    }
  },
  "rooms": [
    {
      "RoomId": {
        "HasValue": true,
        "Value": 5440
      },
      "AutoRecord": {
        "HasValue": true,
        "Value": false
      },
      "RecordMode": {
        "HasValue": false,
        "Value": 0
      },
      "CuttingMode": {
        "HasValue": false,
        "Value": 0
      },
      "CuttingNumber": {
        "HasValue": false,
        "Value": 0
      },
      "RecordDanmaku": {
        "HasValue": false,
        "Value": false
      },
      "RecordDanmakuRaw": {
        "HasValue": false,
        "Value": false
      },
      "RecordDanmakuSuperChat": {
        "HasValue": false,
        "Value": false
      },
      "RecordDanmakuGift": {
        "HasValue": false,
        "Value": false
      },
      "RecordDanmakuGuard": {
        "HasValue": false,
        "Value": false
      }
    }
  ]
}
```
