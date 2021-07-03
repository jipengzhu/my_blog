title: 排序算法之选择排序c语言版
categories:
  - 编程
tags:
  - 算法
date: 2017-07-15 00:04:00
---
# 算法说明

选择排序是一种 **选择类** 的排序算法，也是一种比较直观和容易理解的算法


## 排序过程

1. 在未排序部分中的除第一个元素外的元素里依次选择一个元素
2. 如果这个元素比第一个元素小，就和第一个元素进行交换
3. 经过一趟选择后，最小的元素就出现在了最前面

然后再对剩下的未排序部分的元素重复此过程，直到整个列表有序

### 源代码

{% ghcode https://github.com/jipengzhu/dsa/blob/master/algorithm/sort/sort.h %}

{% ghcode https://github.com/jipengzhu/dsa/blob/master/algorithm/sort/select/simple_select_sort.c %}


## 复杂度
### 时间复杂度
O(n<sup>2</sup>)

### 空间复杂度
O(1)



# 排序优化
我们在选择的过程中同时选择出最小值和最大值，这样比较次数就能够折半

{% ghcode https://github.com/jipengzhu/dsa/blob/master/algorithm/sort/sort.h %}

{% ghcode https://github.com/jipengzhu/dsa/blob/master/algorithm/sort/select/dual_select_sort.c %}


## 复杂度
### 时间复杂度
O(n<sup>2</sup>)

### 空间复杂度
O(1)