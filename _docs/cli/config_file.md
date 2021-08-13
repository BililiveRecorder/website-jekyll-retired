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
