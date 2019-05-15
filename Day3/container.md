## 字典
* 创建<br>
	用花括号括起来，键值对间用逗号隔开，键与值用冒号隔开
	`a = {‘a’:97,’alpha’:[a,b,c,d,e]}`
	>键不可变，用字符串，元组，数字充当
	>键不可重复，如果重复，后出现的会被记住
* 操作<br>
	* 访问<br>
		`for x,y in items()    #返回由键值对组成的元组`<br>
		`for x in keys()       #返回键的迭代器，可用list()转为列表`<br>
		`for x in values()     #返回值的迭代器，可用list()转为列表`<br>
	* 增加<br>
		`a[‘digtal’] = [1,2,3,4,5]  #增加一对`<br>
		`dict.fromkeys(seq,[values])  #序列seq中的是键，values是值，默认为None`<br>
		`dict1.update(dict2)  #用dict2更新dict1,键一样则覆盖，键不同则加入`
	* 删除<br>
		`del a[‘a’]   #删除一对`<br>
		`clear()  #删除所有元素`<br>
		`del a  #删除整个字典`<br>
		`pop(key) #删除指定key对应的键值对`
	* 修改<br>
		`a[‘alpha’] = [A,B,C,D,E]`
	* 查找<br>
		`get(key,default = None) #根据键找值，如果值不在字典中返回default值`
	* 复制<br>
		```
		dic2 = dic1 #浅拷贝: 引用对象
		dic2 = dic1.copy()   # 浅拷贝：深拷贝父对象（一级目录），子对象（二级目录）不拷贝，还是引用
		import copy
		dic2 = copy.deepcopy(dic1) #深拷贝，为父对象与子对象都开辟了新的空间
		```

## 集合(set)：一个无序的不重复元素序列
* 创建<br>
	1.用大括号括住，集合各项用逗号隔开<br>
	2.用set(iterable)创建，参数只能有一个，为可迭代对象，如列表，元组，字符串<br>
	3.空集合只能用set(),不能用{}，因为{}表示空字典<br>
* 操作<br>
	* 增加元素<br>
		添加单个元素，element为集合允许添加的元素即不可变元素(数字，字符串，元组)<br>
		`add(element)`	<br>
		添加多个元素,iterable为可迭代对象(列表，字符串，元组)<br>
		`update(iterable)`<br>
	```
	# 创建集合
	s1 = set('123')
	s2 = set('123')
	s3 = set('abc')

	# 添加单个元素
	s1.add('4')
	
	# 添加多个元素
	s2.update(['4','5','6'])  # 添加列表到集合，列表元素会被分解为单个元素后添加到集合
	s3.update('de')  # 添加字符串到集合，字符串会被分解为单个元素后添加到集合
	
	# 显示输出
	print (s1)  # 显示输出结果为：{'4', '3', '1', '2'}
	print (s2)  # 显示输出结果为：{'4', '2', '6', '5', '3', '1'}
	print (s3)  # 显示输出结果为：{'c', 'b', 'd', 'e', 'a'}
	```
	* 删除元素<br>
		remove(element):删除指定元素，若不存在，抛出异常<br>
		discard(element):删除指定元素，不存在不会抛出异常<br>
		pop():随机删除并返回一个元素<br>
		clear():清空集合

	* 集合运算<br>
		* 交集
			```
			a&b
			a.intersection(b)   #a不会变化
			a.intersection_update(b)  #用交集结果更新a	
			```
		* 并集
			```
			a|b
			a.union(b)
			```
		* 补集
			```
			a - b
			a.difference(b)
			a.difference_update(b)
			```
		* 差集
			```
			a ^ b
			a.symmetric_difference(b)
			a.symmetric_difference_update(b)
			```
##  分支结构<br>
	if-elif-else
## 循环结构<br>
	```
	for <variable> in <sequence>: 
		<statements> 
	else:
		 <statements>
	```
## 三目表达式
	条件为真时的结果 if 判段的条件 else 条件为假时的结果 
