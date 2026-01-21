---
date: 2025-12-06
tags:
  - 计算机科学与技术
  - Python
---
# 介绍

- 类是**面向对象编程**的核心概念，用于**创建具有属性和方法**的对象
>Python的方法类似于函数，但是方法**位于类内部**，方法的第一个参数是`self`，调用方式也不同：函数可以直接调用，而方法需要通过对象调用，如：`date1.add()`，`date1`是对象，`add()`是方法

- **语法**：
```python
class 类的名字:

	def __init__(self, 参数1, 参数2, ...):
        self.属性1 = 参数1
        self.属性2 = 参数2
        # ...
    
    def 方法名(self, 参数):
        # 方法体
        pass
```

>下面进行一一解释

- 位于类中的函数称为方法，对于方法，**函数的一切都适用于方法**
	- 唯一的区别是是**调用方法的方式**

>`__init__()`

- 该方法是一个特殊的方法，当创建类的实例时，python会自动调用这个方法
- `__init__(self, name, age)`
	- **参数先自动传递给`__init__(self, name, age)`**，在这个方法内部初始化属性
	- `self`
		- 在这行代码中`self`是**必须的**，并且还必须位于其他形参之前
		- 是一个指向实例本身的调用
		- 通过`self.属性名`来设置对象的属性，并初始化
		- `self`会自动传递，也就是会自动将该参数传递给方法
	- `name`和`age`
		- `name`和`age`是创建对象时需要传递的参数，也就是**形参**
		- 每一次使用类创建实例时，都只需给他们提供值，而不用给`self`

<br>

- `self.属性1 = 参数1`
	- 前缀`self`，以`self`为前缀的变量都可以给类中的所有方法使用
	- 例如：`self.name = name`，获取存储在形参`name`中的值，并将他存到变量`name`中
	- 像这样可通过实例访问的变量称为属性

<br>

- `def 方法名(self, 参数):`
	- 在类中所有定义的类都需要包含`self`，例如`def add(self):`，无论是否传递参数给`add`，都需要在`()`中包含`self`

# 类的使用

下面是一个创建好的类

```python
class number_handle():
	def __init__(self, a, b):
		self.a = a
		self.b = b
		self.score = 0 #定义并初始化属性
	
	def add(self):
		return self.a + self.b
	
	def lower(self):
		return self.a-self.b
		
	def bigger(self):
		return max(self.a,self.b)
	
	def num(self):
		print(f"This is a one of numbers:{self.score}")
```

>创建实例

```python
# 创建实例  
date1 = number_handle(1,2)  

# 使用  
print(str(date1.a) + '\t' + str(date1.b))  

# 调用类里面的方法  
print(f"两个数相加得到： {date1.add()}")
date1.num()
```

1. 访问属性
	- 句点表示法：`实例名.属性名`
	- 例如：`date1.a`
2. 调用方法处理实例
	- 例如：`date1.add()`，`date1.lower()`

>修改属性的值

1. 直接修改
	- 通过实例直接访问要修改的属性
	- 位于类定义外：`date1.score = 23`，将直接改变类内部的属性值
2. 通过方法修改
	- 在**类内部**定义一个方法用于修改数据
	```python
		def update_score(self, new_date)
			self.score = new_date
	# 上方是类定义一个修改变量的方法
	
	# 下方是调用方法进行修改
	date1.update_score(23) # 修改date1的score属性为23
	date1.num() # 调用num()方法输出
	```

3. 通过方法对属性的值进行递增
	- 在类内部定义一个方法用于递增
```python
	def update_plus_score(self, plus_date)
		self.score += plus_date
# 上方是类定义中递增的方法

# 下方是调用方法进行修改并输出
date1.update_plus_score(43)
date1.num() # 调用num()方法输出
```

# 类的继承

>编写类的时候，并不总是要从0开始写，如果要编写的类是另一个类的特殊版本，可以使用继承
>
>>一个类继承另一个类的时候，自动获得另一个类的所有属性和方法，同时还可以定义自己的属性和方法
>
>>原来被继承的类被称为**父类**，新的类被称为**子类**

<br>

### 子类的方法`__init__()`

>创建子类的实例时，Python首先需要完成的任务是给父类的所有属性赋值，为此，子类的方法`__init__()`需要父类的帮助

- 创建子类时，父类**必须**包含在当前文件中，并且**位于子类的前面** 

<br>

- 定义子类时，**括号内必须指定父类的名称**，如`class electriccar(Car)`  
	- 其中，`Car`是父类的名称

<br>

- 方法`__init__()`**接受创建父类时所需的信息**，例如：`__init__(self,make,model,year)`，假设`model,make,year`是父类创建时包含的信息 

<br>

- 使用`super().__init__(make,model,year)`帮助子类和父类关联起来，**使得子类包含父类的所有属性** 

<br>

>[!note]- 给子类定义属性和方法
>
>```python
># 假设上面定义了一个父类Car
>	class electriccar(Car):
>		"""假设make,model,year都是父类的参数"""
>		def __init__(self,make,model,year):
>			super().__init__(make,model,year)
>			
>			"""定义并初始化子类的属性"""
>			self.battery_size = 70
>		
>		def describe_battery(self):
>			print(f"This car has a {self.battery_size}KWh battery.") 
>```

<br>

- **在子类中重写父类的方法**：只要在子类中定义的方法与父类的方法同名，那么就不会考虑父类的同名方法，而使用子类的方法

- **将实例用作属性**：创建一个新类用于处理实例
	```python
	# 上方还有一个Car父类
	class Battery():
		def __init__(self,battery_size):
		# 初始化属性
			self.battery_size = battery_size

		def  describe_battery(self):
			print(f"This car has a {self.battery_size}KWh battery.")
	class electriccar(Car):
	
	# 此处省略部分为之前的代码
	
		super().__init__(make,model,year)
		
		# 这里添加一个self.battery属性，并创建一个新的Battery实例
		self.battery = Battery()
		# 因此，现在每一个electriccar实例都将包含一个Battery实例
	```
	这样的好处是，我们可以更多的丰富battery的细节，而不用担心某一个类过于臃肿

<br>

# 类的导入
`类似模块的导入`

>导入单个类
- `from car import Car`：从`car.py`模块中导入`Car`类
	- `car.py`模块中只包含了一个`Car`类
- 如果`car.py`模块中包含多个类，并且**导入的一个类还包含了其他类的属性**
	- 这样的情况对正常使用没有影响，仅仅只能使用导入的类的属性和方法

<br>

>导入多个类
- `from car import Car,electriccar`，导入`Car`和`electriccar`两个类

>导入整个模块

- `import car`，导入`car.py`模块

>导入模块中的所有类（==不推荐==）

- ` from car import *`，导入模块`car.py`中的所有类

>在一个模块中导入另一个模块

- 假设有两个文件`car.py`和`electric_car.py`
	- `from car import Car`，在`electric_car.py`中导入`car.py`模块的`Car`类