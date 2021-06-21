---
title: 录播姬命令行版
permalink: /docs/cli/
---

录播姬命令行版可以在 Windows, Mac, Linux (x64, arm, arm64) 上运行。

从 1.3 开始命令行版将与桌面版同步发布版本，可在本项目 GitHub 仓库的 Releases 页面下载。  
下载地址： <https://github.com/Bililive/BililiveRecorder/releases>  
也可以从 GitHub Actions 里来源分支为 `dev-1.3` 的 Build 的 Artifacts 里下载使用，不过开发版不保证稳定可靠。

Docker 版见 [录播姬 Docker 版](/docs/cli/docker/)

因为命令行版暂无交互界面和接口，只能读取配置文件运行，所以目前不建议一般用户使用。  
以后（不是近期）应该会增加 Web 界面和 HTTP API。

录播姬命令行版与桌面版的功能完全一致，两个版本共用同一套核心代码，只在与用户交互的外壳代码上不同。  
录播姬命令行版与桌面版的配置文件也是通用的，可以在桌面版配置好相关参数后用命令行版加载运行。  
本站文档里所有内容对命令行版也有效。

录播姬命令行版也提供了与桌面版一样的完整的录播姬工具箱功能，便于有能人士编写脚本实现自动化。

录播姬命令行版的用法见 `--help` 的输出，下面给出部分示例

```sh
# 标准（使用配置文件）模式运行
./BililiveRecorder.Cli run "/path/to/target"

# 无配置文件模式运行
./BililiveRecorder.Cli portable "/path/to/output" 1 2 3 4 5

# 使用工具箱分析录播文件并以 json 格式输出到 stdout
./BililiveRecorder.Cli tool analyze "/path/to/recording.flv" --json
```
