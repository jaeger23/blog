---
layout: default
title: Android Studio 快捷键(OS X 下)
---

### Android Studio 快捷键 （OS X）
[原文连接](http://www.blueowls.net/android-studio-%E5%B8%B8%E7%94%A8%E5%BF%AB%E6%8D%B7%E9%94%AE/)

*Android Studio 已确认快捷键, 选择Keymaps: Mac OS X 10.5+*

### 查找/替换方面

- 普通查找: command+F   
- 替换文本: command+R   
  需要全局的, 都在原基础上加 Shift
- SearchEverywhere: shift * 2
- 查找搜索结果的前/后续同名: command+G / command+shift+G
- 高亮显示所有选中文本: Ctrl+Shift+F7 , 按Esc高亮消失
- Selete All Occurrences: ctrl + command + G
- Select Next Occurrence: ctrl + G

### 快速打开方面
- 打开文件: command + shift + O
- 打开近期文件: command+E
- 打开 Task: option+shift+N
- 新窗口打开文件: shift + F4

### 导航跳转
- 跳转到上方文件导航: command+向上箭头
- 跳转到上一步/下一步: command+[ / command + ]
- Previous /Next Occurrence: option + command + up/down
- 上一处编辑地点: shift + command + delete
- 左右切换代码标签页: command+shift+[ / Command+shift+]
- 跳转指定行数: command+L
- 添加书签: F3
- 添加带有数字书签点: option + F3
- 展示书签列表: command + F3
- 函数块跳转头尾: command + option + [ / ]
- 返回到上一个 tool window: F10 (原版 F12)
- 复制整行: command + D
- 删除整行: command+delete, Ctrl+X
- 删除光标前面内容: command + delete
- 删除单词到头部: option + 前删除
- 删除单词到尾部: option + 后删除
- 开启新一行: shift + Enter
- 大小写转换: command + shift + U
- 从剪切板缓存中复制: command + shift + V
- 上下Statement行: command + shift + Up/Down
- 上下Line行: option + shift + Up/Down
- 区块只能选择: option+up/down
- 返回到主编辑窗口: esc
- 隐藏活动中的工具窗口: shift + esc

### 代码生成/提示方面
- 基础代码生成: ctrl + space.
- 智能代码生成(更匹配当前上下文方法及变量): ctrl + shift + space
- 完成代码语句: command + shift + enter
- 上下文神Key, 展示意图与行为及quick fixed: option+Enter
- 循环推荐单词内容: option + /. option + shift + /
- 方法参数提示: command + P
- 类名或接口名提示, 简单查看本类元素. 类名填写完整: ctrl+option+Space
- 快速加上 If/For/While/TryCatch: command+option+T
- 生成代码列表: command + N
- 自动提示内嵌快捷键: command + J
- 快速代码变普通注释: command+/
- 快速代码变块注释/**/: command + option + /. ctrl + shift + /.

### 文档/信息查看方面
- 查看 Doc 描述: ctrl +J / F1
- 简短信息查看: command
- 错误信息查看: command + F1
- 上下文信息 Context Info: ctrl + shift + Q
- 高亮错误或警告快速定位: F2 或Shift+F2
- 系统修改建议 Option+Enter：当IDE提示warning和error时，使用这个组合键查看修改建议。
- 展开与关闭区块: command + “+/-”
- 展开与关闭所有区块: command + Shift + “+/-”
- 关闭当前Tab: command + W
- 代码查找方面
- 打开类: command + O
- 打开代码元素: command + option + O
- 文件结构内容(本类元素内容): command + F12
- 文件路径: option + command + F12

- Find usages 查看全局引用: option + F7
- Find usages in file: command + F7
- Show usages: command + option + F7
- Highlight usages in file: command + shift + F7
- 重载函数列表: ctrl + O
- 函数实现列表: ctrl + I
- 代码生成基础列表: command+N / Ctrl+Enter

- Type Hierarchy: ctrl+H
- Method Hierarchy: command+shift+H
- Call Hierarchy: ctrl+option+H

- show source: ctrl+Enter
- 跳转到声明区: command + B, command+ 鼠标点击
- 跳转到被实现点: command+option+B
- 打开快去查看查看声明描述: command+Y.
- 查看某个接口的实现, 查看实现类: ctrl + shift + B
- 查看父类或者父亲函数点: command + U
- 查看代码源码点: F4, command + 下箭头

### Debug
- Run: ctrl + R
- Debug: ctrl + D
- Stop: command + F2
- StepOver: F8
- Force StepOver: option + shift + F8
- StepInto: F7
- Force StepInto: option + shift + F7
- Smart StepInto:shift + F7
- Step Out: shift + F8
- Run to Cursor: option + F9
- Resume Program: option + command + R
- Evaluate Expression: option + F8
- Quick Evaluate Expression: option + command + F8. option + left click
- Show Execution Point: option + F10
- Toggle Line Breakpoint: F8
- Toggle Temporary Line Breakpoint: option+ shift + command + F8
- View Breakpoints: shift + command + F8

### 代码重构方面
- 代码快速 format: command+Option+L
- 整理import: ctrl + option + O
- 复制类: F5
- 移动类: F6
- 安全删除某个元素: command + delete
- 重命名: shift + F6
- 修改方法签名 Command+F6
- 重构列表: ctrl + T

<p>{{ page.date | date_to_string }}</p>