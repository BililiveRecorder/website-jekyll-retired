---
title: 录播修复 - 工具箱
---

录播修复可以使用录播姬里的录播修复系统对视频文件进行分析、修复，还可以导出原始分析数据。

## 用法

选择 FLV 文件，然后点“分析”或“修复”按钮，或点“修复失败？”后点击“导出原始分析数据”。

关于能修复什么文件、能修复什么样的问题，见 [录播修复介绍](/docs/process/)

## 命令行版

```sh
# 工具箱用法
./BililiveRecorder.Cli tool --help

# 分析
./BililiveRecorder.Cli tool analyze "input.flv"

# 修复
./BililiveRecorder.Cli tool fix "input.flv" "output.flv"

# 导出分析数据
./BililiveRecorder.Cli tool export "input.flv" "output.brec.xml.gz"
```
