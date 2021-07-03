title: 排序算法之希尔排序c语言版
categories:
  - 编程
tags:
  - 算法
date: 2017-07-15 00:07:00
---
# 算法说明

希尔排序是对插入排序的增强


## 排序过程

1. 选择一个增量因子t1，t2，…，tk，其中ti > tj，tk=1
2. 然后根据对应的增量ti，将待排序列分割成若干长度为m的子序列并排序

直到增量因子为1并且排序后，整个列表就会有序

### 源代码（for循环版本）

{% ghcode https://github.com/jipengzhu/dsa/blob/master/algorithm/sort/sort.h %}

{% ghcode https://github.com/jipengzhu/dsa/blob/master/algorithm/sort/shell/shell_sort_for.c %}

> 边界判断：
> 因为 i + d <= n - 1， 所以 i + d < n
> 别忘了 j >= 0


### 源代码（while循环版本）

{% ghcode https://github.com/jipengzhu/dsa/blob/master/algorithm/sort/sort.h %}

{% ghcode https://github.com/jipengzhu/dsa/blob/master/algorithm/sort/shell/shell_sort_while.c %}

> 边界判断：
> 因为 i + d <= n - 1， 所以 i + d < n
> 别忘了 j >= 0


## 复杂度
### 时间复杂度
时间复杂度受增量因子影响，所以无法简单估计

### 空间复杂度
O(1)