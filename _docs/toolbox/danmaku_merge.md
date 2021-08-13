---
title: 弹幕合并 - 工具箱
---

弹幕合并工具可以合并多个录播姬录制的XML弹幕文件。  
录播姬会自动根据弹幕文件里的时间信息调整合并成一个文件。  
此工具只支持合并录播姬录出的弹幕XML文件。

## 用法

点击 添加文件 按钮添加弹幕文件，或把弹幕XML文件拖入合并界面。再点击 合并 按钮，选择合并后的弹幕文件保存位置。

## 命令行版

```sh
./BililiveRecorder.Cli tool danmaku-merge "output.xml" "input1.xml" "input2.xml" "input3.xml"
```
