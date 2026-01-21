---
date: 2025-11-16
tags:
  - 计算机科学与技术
  - Python
  - 语言
---
# 输入

###### `input()`的工作原理

- `input()`函数让程序暂停运行，等待用户输入一些文本。获取用户输入后，Python将其存储在一个变量中，以方便使用
- 同时，还兼顾了一部分输出的功能，例如`input("请输入文本")`，将会

###### `int()`转换

- 将数字的字符串表示转换为数值表示
- 只能将字符串转换为数字，不能输入

# `while`循环

- 语法：
`while 循环条件:`
	`#循环体`
- 与C中类似：例如`while num < 10:`

循环退出方法：与C类似：使用`break`，`continue`，具体意义和C中一样

### `while-else`结构

```python
count = 1
while count <= 3:
	print(f"Count:{count}")
	count += 1
else:
	print("结束了")
```

- 该语法类似`if-else`

>`pass`：占位符