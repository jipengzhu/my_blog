title: 排序算法之大堆排序c语言版
categories:
  - 编程
tags:
  - 算法
date: 2017-07-15 00:10:00
---
# 算法说明

大堆排序是一种 **交换类** 的排序算法，也是一种比较高效的算法


## 排序过程

1. 将`未排序部分`自底向上构建为一个满二叉树，树的父结点大于子结点
2. 则根结点为最大的结点，将根结点和未排序部分的尾部交换，称为大堆排序

然后再对剩下的未排序部分的元素重复此过程，直到整个列表有序

### 源代码

{% ghcode https://github.com/jipengzhu/dsa/blob/master/algorithm/sort/sort.h %}

{% ghcode https://github.com/jipengzhu/dsa/blob/master/algorithm/sort/heap/heap_sort.c %}


## 复杂度
### 时间复杂度
O(nlog<sub>2</sub>n)

### 空间复杂度
O(1)