---
date: 2025-12-06
tags:
  - 计算机科学与技术
  - Python
---
# 定义函数

- 使用`def 函数名(参数1，参数2……):`，进行定义
	- 具体使用方法与C类似
- 不同点：无返回值不使用`return`即可

>[!code]- 
>```Python
># 下面这个函数的作用就是输出a到b的所有数  
>def num(a,b):  
>    for value in range(a,b+1):  
>        print(f"{value}\t",end="")  
>  
>#下面这个函数的作用是输出a和b的和  
>def add(a,b):  
>    return a+b  
 > 
>num1 = int(input("Enter a number: "))  
>num2 = int(input("Enter another number: "))  
>num(num1,num2)  
>print('\n')  
>print(add(num1,num2))
>```

下面是输出：
```text
3	4	5	6	7	8	9	

12

```

- 在Python中也有形参和实参的概念，具体请参考C语言

# 给函数传递参数

> 给函数传递任意数量的实参


```python
def num(*n):
	print(n)
num(3,1,5,7)
```

- `*n` 中的`*`是让Python创建一个名为`n`的空元组，并将收到的所有值都封装到这个元组中
- 如果要**让函数接受不同类型的实参**，**必须**在函数定义中**将接纳任意数量实参的形参放在最后**

例如：`def num(size, *n):`

- 对于字典：
	- `def date(first, last, **info):`

