### 一、list列表

#### 1.概述

> 引出：存储一个数据可以采用变量
>
> 解决：容器【Python提供了一种数据结构list，可以同时存储多个数据】
>
> 本质：一种有序的集合

#### 2.创建列表

> 语法：列表名 = [列表选项一，列表选项二，列表选项三.....]
>
> 说明：使用[]表示列表，列表名其实就是标识符
>
> ​	    将列表中的列表选项被称为元素
>
> ​	     列表中的元素分别被编了号，这些编号被称为索引【下标，角标】，从0开始编号

#### 3.列表中元素的访问

##### 3.1取值

> 语法：列表名[索引]
>
> ```Python
> list4 = [100,200,400,300,800]
> num = list4[2]
> print(num)
> print(list4[2])
> ```

##### 3.2替换

> 语法：列表名[索引] = 新的元素值
>
> ```Python
> list4[2] = 888
> print(num)
> print(list4[2])
> ```

#### 4.列表操作

> ```Python
> #1.列表组合
> #直接使用加号
> list1 = [43,65,76,6]
> list2 = [45,77,90,11,2,4,66]
> print(list1 + list2)
>
> #2.列表重复
> #直接使用乘号
> print(list1 * 4)
>
> #3.判断指定元素是否存在于列表中
> #成员运算符：in      not in
> #运算的结果为布尔值
> list3 = ["hello",False,189,"good"]
> print(189 in list3) #True
> print(180 not in list3)  #True
>
> #4.列表的截取【分片，切片】
> #语法：列表名[开始下标:结束下标]，表示获取从开始下标到结束下标之间的元素，结果为一个新的列表
> #注意：包头不包尾【前闭后开区间】   [开始下标,结束下标)
> list4 = ["hello",False,189,"good",436,54,3,45]
> print(list4[2:4])
>
> #获取从指定下标到结尾的列表，包含指定下标
> print(list4[3:])
>
> #获取从开头到指定下标的列表，不包含指定下标
> print(list4[:6])
> ```

#### 5.列表内置功能

> 语法：列表名.功能()
>
> ```Python
> #一、添加元素
> #1.append   在列表结尾添加元素或者新的列表【追加】
> list11 = [1,2,3,4,5]
> print(list11)
> #追加元素
> list11.append(100)
> print(list11)
> #追加列表【将容器和元素一起添加进去】
> list11.append([547,76,87])
> print(list11)
>
> #2.extend    在列表的末尾一次性追加另一个列表中的元素
> list12 = [1,2,3,4,5,100]
> list12.extend([547,76,87]) #只将元素添加进去
> print(list12)
>
> #3.insert  在指定索引处插入一个元素，不覆盖原来的元素，原有的元素向后顺延
> #注意：告诉编译器，需要在什么位置插入什么元素
> list13 = [1,2,3,4,5]
> print(list13)
> #插入元素
> list13.insert(2,555)
> print(list13)
> #插入列表
> list13.insert(4,[22,33])
> print(list13)
>
> #二、移除元素
> #4.pop   移除列表中指定下标的元素
> list14 = [1,2,3,4,5,100]
> print(list14)
> #默认移除最后一个元素
> list14.pop()
> print(list14)
> #移除指定下标的元素
> list14.pop(3)
> print(list14)
>
> #5.remove  移除元素
> list15 = [11,23,354,45,5,100]
> #如果元素不存在，则出现错误：ValueError: list.remove(x): x not in list
> #list15.remove(3)
> list15.remove(5)
> print(list15)
>
> #6.clear   清空列表
> list16 = [11,23,354,45,5,100]
> list16.clear()
> print(list16)
>
> #三、获取
> #7.index   从列表中查询第一个匹配的元素的下标
> list17 = [11,23,354,45,5,100,100,23,354]
> print(list17)
> #在整个列表中查询
> print(list17.index(23))
> #只在部分列表中查询【包头不包尾】
> #注意：2和7表示开始下标和结束下标
> #print(list17.index(23,2,7))
>
> #获取相关信息，语法：功能()
> #8.len 获取列表中元素的个数【获取列表的长度】
> list18 = [11,23,354,45,5,100,100,23,354]
> #注意：len直接使用
> print(len(list18))
>
> #9.max  获取列表中的最大值
> print(max(list18))
>
> #10.min  获取列表中的最小值
> print(min(list18))
>
> #11.count  查看元素在列表中出现的次数
> print(list18.count(23))
>
> #四、反转
> #12.reverse  将列表实现倒序
> list18.reverse()
> print(list18)
>
> #五、排序
> #sort和sorted
> #13.sorted
> list19 = [11,23,354,45,5,100,100,23,354]
> #默认实现升序排序
> list1 = sorted(list19)
> print(list1)
> #可以实现降序排序
> list2 = sorted(list19,reverse=True)
> print(list2)
>
> #通过key关键字来实现排序：根据字符串的长度排序
> list20 = ["zoo","manager","hello","jack","international"]
> list3 = sorted(list20,key=len)
> print(list3)
>
> #14.sort
> list19.sort()  #升序
> print(list19)
> list19.sort(reverse=True)  #降序
> print(list19)
>
> #六、拷贝【面试题】
> #浅拷贝：引用拷贝
> list21 = [1,2,3,4,5]
> list22 = list21
> print(list21)
> print(list22)
> list22[2] = 100
> print(list21) #[1, 2, 100, 4, 5]
> print(list22) #[1, 2, 100, 4, 5]
>
> #深拷贝：拷贝内容
> #15.copy
> list23 = [1,2,3,4,5]
> list24 = list23.copy()
> print(list23)
> print(list24)
> list24[2] = 666
> print(list23) #[1, 2, 3, 4, 5]
> print(list24) #[1,2,666,4,5]
> ```

#### 6.二维列表

> 实质上还是一个简单列表，只不过列表的元素仍然是一个列表
>
> 代码演示：
>
> ```Python
> list1 = [[11,22,33],[100,100],[438,4,4,3,21]]
> ```
>

### 三、for-in循环

#### 1.用法

> 语法：
>
> for 变量名 in 列表：
>
> ​	语句
>
> 说明：主要用于遍历列表【遍历：依次访问列表中的每一个元素,获取元素值】
>
> 工作原理：按照顺序获取列表中的每个元素，赋值给变量，再执行语句，以此类推，直到列表中的元素全部获取为止
>
> 举例：
>
> ​	list1=[1,2,2,5,6]
>
> ​	print(list1[2])

#### 2.列表生成器

> ```Python
> #列表生成器
> #
> """
> range([start,]end[,step])
> 说明：start表示开始的值，end表示结束的值，step表示步长
> 其中，start和step可以省略，start默认为0，step默认为1
>
> 功能：生成指定的列表
>
> 例如：
> range(100):可以生成一个0~99的整数列表
> range(1,100):可以生成一个1~99之间的整数列表
> range(1,100,2):可以生成一个1~99的奇数列表
> """
>
> #需求一：1~100之间所有整数的和
> num = 1
> sum = 0
> while num <= 100:
>     sum += num
>     num += 1
>
> sum1 = 0
> for n in range(1,101):
>     sum1 += n
>
> #需求二：计算1~100之间所有偶数的和
> sum2 = 0
> for n in range(1,101):
>     if n % 2 == 0:
>         sum2 += n
>
> sum4 = 0
> for n4 in range(0,101,2):
>     sum4 += n4
>
> sum3 = 0
> num3 = 1
> while num3 <= 100:
>     if num3 % 2 == 0:
>         sum3 += num3
> ```

#### 3.同时遍历列表中的元素和下标

> ```Python
> #同时遍历列表中的元素和下标
> list1 = [43,54,65,76,7,878]
>
> #index表示下标，num表示元素值
> #enumerate
> for index,num in enumerate(list1):
>     print(index,num)
>
> #需求：输出列表中偶数下标对应的元素
> for n in list1:
>     print(n)
>
> for index,num in enumerate(list1):
>     if index % 2 == 0:
>         print(index, num)
>
> ```

#### 4.嵌套for循环

