title: 排序算法之归并排序c语言版
categories:
  - 编程
tags:
  - 算法
date: 2017-07-15 00:09:00
---
# 算法说明

归并排序是一种 **分治+归并类** 的排序算法，也是一种比较高效的算法


## 排序过程

1. 将`未排序部分`分为两部分，并在两部分中选择出较小元素的追加到新的数组
2. 然后将剩余部分的元素都追加到新的数组中，这样右边的部分就会比左边的部分都大

然后再对两边的元素分别重复此过程，直到整个列表有序

### 源代码

{% ghcode https://github.com/jipengzhu/dsa/blob/master/algorithm/sort/sort.h %}

{% ghcode https://github.com/jipengzhu/dsa/blob/master/algorithm/sort/merge/merge_sort.c %}


## 复杂度
### 时间复杂度
O(nlog<sub>2</sub>n)

### 空间复杂度
O(n)