# LinkNode
笔记管理器 = 笔记管理 + 笔记编辑
笔记 = 文本 + 画图

# 编辑器

## 输入处理
- `contentEditable`
- `textarea` 模拟


## 光标处理

使用 `div` 模拟光标

光标位置计算
- 基于 `window.getSelection()`
- 模拟计算


### 文本长度计算
- 单一字体
  - 等宽字体 Monospaced Font
  - 非等宽字体
- 混合字体

## 框选
- `window.getSelection()`
- 模拟计算（`div` 选择层）


### 问题
`window.getSelection()`
- 多选支持有限
- Chromium、Firefox 实现不一样

## 编辑处理
问题：
- 字符
- 粘贴
- 输入法 见：[IME](#IME)

解决方法：
`TextArea` 跟随，作为输入焦点，处理 `change` 事件。

`change` 与 `input` 的区别：
- `input`: `element.value` 值改变的时候触发
- `change`: 用户提交修改的时候触发

## IME
处理三个事件：
- `compositionStart`
- `compositionUpdate`
- `compositionEnd`


# Parser



# 画板

## 实现
基于 `canvas`

## 笔迹处理

## 历史记录
