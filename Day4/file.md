## 文件
### 打开文件<br>
通常使用open(file, mode='r')，以只读方式打开
常用mdoe参数：<br>
a	用于在文件尾追加<br>
b	以二进制打开<br>
/+	更新操作，可读可写<br>	
r	只读<br>
w	打开用于写入，从开头写，原内容会被删除<br>
### 读取文件内容<br>
read():一次性全部读到内存中，用str对象表示。若文件10g，那8g内存就炸了
read(size)：size指定读入字符的数目，一个汉字也是1,一个字符也是1
readline(): 读取一行内容，用str返回
readlines()：一次性读取所有行，按行返回一个list
### 写文件<br>
write(str):可以反复调用write来写
>写文件时，操作系统往往不会立刻把数据写入磁盘，而是放到内存缓存起来，空闲的时候再慢慢写入。只有调用close()方法时，操作系统才保证把没有写入的数据全部写入磁盘。
### 关闭文件<br>
close()
### 为了避免因为异常而导致文件没有正确被关闭，采用with语句来进行文件的操作
```
with open('/Users/michael/test.txt', 'w') as f:
    f.write('Hello, world!')
```
## 操作excel文件
xlrd模块：用于读取excel
xlwt模块：创建新的excel表格，写入内容及保存
xlutils模块：修改excel表格
### 读取
```
import xlrd
data = xlrd.open_workbook(r"/home/sva/Python/exceltest.xls")  #打开文件
table1 = data.sheets()[0]	#读一张表
nrows = table.nrows  #获取行数
ncols = table.ncols	#获取列数
print(table.row_values(0))  #读一行
print(table.cell_value(0,0)) #读一个单元格
```
### 创建
```
import xlwt
workbook = xlwt.Workbook(encoding='utf-8', style_compression=0) #新建文件
sheet = workbook.add_sheet('test', cell_overwrite_ok=True)		#新建表格
sheet.write(0, 0, 'EnglishName')  #向单元格写入数据
sheet.write(1, 0, 'Marcovaldo')
workbook.save(‘/home/sva/Python/writetest.xls’)   #保存
```
### 修改
```
import xlutils.copy                                                    
data = xlrd.open_workbook(r'/home/sva/Python/writetest.xls')           
ws = xlutils.copy.copy(data)                                           
table = ws.get_sheet(0)                                                
table.write(2,0,"三")                                                  
table.write(2,1,"吃")                                                  
ws.save(r'/home/sva/Python/writetest.xls')  
```
## 操作CVS文件
需导入cvs库
### 读取
* 读取第一行
···
#方式一
import csv
with open("D:\\test.csv") as f:
    reader = csv.reader(f)
    rows=[row for row in  reader]
    print(rows[0])
----------
#方式二
import csv
with open("D:\\test.csv") as f:
    #1.创建阅读器对象
    reader = csv.reader(f)
    #2.读取文件第一行数据
    head_row=next(reader)
    print(head_row)
···
* 读取第一列
```
import csv
with open("D:\\test.csv") as f:
    reader = csv.reader(f)
    column=[row[0] for row in  reader]  #遍历行，取每行第一个，组成列表，即为第一列
    print(column)
```
* 写入数据
···
import csv
with open("D:\\test.csv",'a') as f:
     row=['曹操','23','学生','黑龙江','5000']
     write=csv.writer(f)
     write.writerow(row)
     print("写入完毕！")
···

## OS模块
用于处理文件和目录
```
#getcwd() 获取当前工作目录(当前工作目录默认都是当前文件所在的文件夹)
#chdir()改变当前工作目录
#mkdir()  创建文件夹
#makedirs()  递归创建文件夹
#rmdir() 删除空目录
#removedirs 递归删除文件夹  必须都是空目录
```
## DateTime模块
由很多时间相关的类组成
* date类
* time类
* datetime类
* timedelta类
