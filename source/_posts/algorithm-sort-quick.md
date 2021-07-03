title: 排序算法之快速排序c语言版
categories:
  - 编程
tags:
  - 算法
date: 2017-07-15 00:08:00
---
# 算法说明

快速排序是一种 **分治+交换类** 的排序算法，也是一种比较高效的算法


## 排序过程

1. 在`未排序部分`中的选择一个元素做为基数
2. 将小于基数的元素放到左边，大于基数的元素放到右边
3. 经过一趟排序后，最后将基数放置到左右两部分的中间位置

然后再对基数两边的元素重复此过程，直到整个列表有序

### 源代码

{% ghcode https://github.com/jipengzhu/dsa/blob/master/algorithm/sort/sort.h %}

{% ghcode https://github.com/jipengzhu/dsa/blob/master/algorithm/sort/quick/quick_sort.c %}


## 复杂度
### 时间复杂度
O(nlog<sub>2</sub>n)

### 空间复杂度
O(1)



# 排序优化
如果序列过于庞大，会导致堆栈调用过深而超过限制，这时需要对堆栈调用的次数进行限制

{% ghcode https://github.com/jipengzhu/dsa/blob/master/algorithm/sort/sort.h %}

{% ghcode https://github.com/jipengzhu/dsa/blob/master/algorithm/sort/quick/quick_sort_limit.c %}


## 复杂度
### 时间复杂度
O(nlog<sub>2</sub>n)


### 空间复杂度
O(1)