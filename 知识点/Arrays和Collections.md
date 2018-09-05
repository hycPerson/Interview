<!-- TOC -->

- [Arrays](#arrays)
    - [排序](#排序)
    - [asList](#aslist)
    - [equals(a,b);](#equalsab)
    - [fill方法](#fill方法)
    - [BinarySearch](#binarysearch)
    - [toString方法是把数组转换成字符串进行输出](#tostring方法是把数组转换成字符串进行输出)
    - [copyof把一个数组复制出一个新数组（新数组的长度为length）](#copyof把一个数组复制出一个新数组新数组的长度为length)
    - [sort(list);](#sortlist)
    - [shuffle(list);](#shufflelist)
    - [获取集合最大值、最小值](#获取集合最大值最小值)
    - [binarySearch](#binarysearch)
    - [indexOfSubList](#indexofsublist)
    - [reverse(list2);](#reverselist2)
    - [rotate(list2, 3);](#rotatelist2-3)
    - [copy(list2, list3);](#copylist2-list3)
    - [swap(list2, 0, 3);](#swaplist2-0-3)
    - [fill(list2, "替换");](#filllist2-替换)
    - [synchronizedList](#synchronizedlist)
    - [synchronizedMap](#synchronizedmap)
    - [synchronizedSet](#synchronizedset)
    - [singleton()](#singleton)

<!-- /TOC -->
### Arrays
数组的处理类
#### 排序
#### asList
Java 细节（2.1）：在使用 asList 时不要将基本数据类型当做参数。
基本类型数组，就是遍历添加进去
#### equals(a,b);
比较两个数组值是否相等
#### fill方法
把整个数组里的每一个元素的值进行替换为val。（void fill(Arrays,val)）
#### BinarySearch
#### toString方法是把数组转换成字符串进行输出
#### copyof把一个数组复制出一个新数组（新数组的长度为length）
 int[]ints2=Arrays.copyOf(ints,ints.length);

 ### Collections
 集合的工具类
#### sort(list);
#### shuffle(list);
#### 获取集合最大值、最小值
#### binarySearch
#### indexOfSubList
查找子串在集合中首次出现的位置
这里的子串指的是子List集合
#### reverse(list2);
反转集合中的元素的顺序
#### rotate(list2, 3);
集合中的元素向后移动k位置，后面的元素出现在集合开始的位置
#### copy(list2, list3);
将集合list3中的元素复制到list2中，并覆盖相应索引位置的元素
#### swap(list2, 0, 3);
交换集合中指定元素的位置
#### fill(list2, "替换");
交换集合中指定元素的位置

#### synchronizedList
#### synchronizedMap
#### synchronizedSet
#### singleton()
singleton(T) 方法用于返回一个不可变集只包含指定对象。