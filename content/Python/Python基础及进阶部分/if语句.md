---
date: 2025-11-15
tags:
  - 计算机科学与技术
  - Python
  - 语言
---
依旧和C语言类似，有着if语句用法也是类似的
# 简单了解

###### 基础语法：

```text
if 条件:
	执行语句#条件为真时执行的代码
```
<br>

```text
if 条件:
	执行语句#条件为真时执行的语句
else:
	执行语句#条件为假时执行的语句
```
<br>

```text
if 条件1:
	执行语句#条件1为真执行
elif 条件2:
	执行语句#条件2为真执行
......
```

###### 条件测试

示例：
`if-else`
>[!example]- 
>代码：
>```python
>car = 'bTR'
>if car == 'bTR':
>	print(car.upper())
>else:
>	print(car.lower())
>```
>
>输出：
>```text
>BTR
>```

`if-elif-else`
>[!example]- 
>代码：
>```python
>age = 12
>
>if age < 4:
>	print("Your admission cost is $0.")
>elif age < 18:
>	print("Your admission cost is $5.")
>else:
>	print("Your admission cost is $10.")
>```
>输出：
>```text
>Your admission cost is $5.
>```

<br>

# 检查条件

###### 使用`and`检查多个条件

如果要多个条件都为`True`时，执行语句，那么可以使用`and`来把两个条件测试合并

- 例如：
```python
age_male = 18
age_female = 20
if age_male==18 and age_female==20:
	print('Yes')
else:
	print('No!')
```

- 输出：
```text
Yes
```

###### 使用`or`检查多个条件

该条件判断类似逻辑运算符`||`，只要一个条件满足，则整个条件就为`True`

- 例如：
```python
age0 = 22
age1 = 18
if age0>=20 or age_female>=20:
	print('Yes')
else:
	print('No!')
```

- 输出：
```text
Yes
```

###### 检查特定值是否在列表中

如果要实现检查特定值，可以使用关键字`in`

- 例子：
```python
num = [1,2,3,4,5]
if 6 in num:
	print(1)
else:
	print(0)
```

- 输出：
```text
0
```

###### 布尔表达式

布尔表达式只有两个返回结果：`True`和`False`

- 当列表元素为空，即不包含任何元素的时候，这时候，列表就相当于`False`
- 例：
```python
num = []
if num:
	for value in num:
		print(value)
else:
	print("There is no number")
```

输出：
```text
There is no number
```

