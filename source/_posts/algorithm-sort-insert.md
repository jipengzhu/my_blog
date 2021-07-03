title: 排序算法之插入排序c语言版
categories:
  - 编程
tags:
  - 算法
date: 2017-07-15 00:06:00
---
# 算法说明

插入排序是一种 **插入类** 的排序算法，也是一种比较直观和容易理解的算法


## 排序过程

1. 在`未排序部分`的元素中选取第一个元素和已排序的部分`自后向前`进行比较
2. 如果被比较的元素大，则被比较的元素向后移动，如果被比较的元素小，则停止比较
3. 将`未排序部分`的元素中选取的第一个元素放置到应插入的位置，即最后被比较的元素的后面

然后再对剩下的`未排序部分`的元素重复此过程，直到整个列表有序

### 源代码（for循环版本）

{% ghcode https://github.com/jipengzhu/dsa/blob/master/algorithm/sort/sort.h %}

{% ghcode https://github.com/jipengzhu/dsa/blob/master/algorithm/sort/insert/insert_sort_for.c %}

> 别忘了 j >= 0

### 源代码（while循环版本）

{% ghcode https://github.com/jipengzhu/dsa/blob/master/algorithm/sort/sort.h %}

{% ghcode https://github.com/jipengzhu/dsa/blob/master/algorithm/sort/insert/insert_sort_while.c %}

> 别忘了 j >= 0


## 复杂度
### 时间复杂度
O(n<sup>2</sup>)

### 空间复杂度
O(1)