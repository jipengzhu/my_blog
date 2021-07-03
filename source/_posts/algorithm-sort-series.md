title: 排序算法之序列排序c语言版
categories:
  - 编程
tags:
  - 算法
date: 2017-07-15 00:11:00
---
# 桶排序

## 算法说明

桶排序是一种 **归并+分治类** 的排序算法，是一种用空间换时间的算法


## 排序过程

1. 将数据根据区间分散到桶中
2. 对各个桶里的数据进行排序
3. 将各个桶里的数据进行合并

### 源代码

{% ghcode https://github.com/jipengzhu/dsa/blob/master/algorithm/sort/sort.h %}

{% ghcode https://github.com/jipengzhu/dsa/blob/master/algorithm/sort/series/bucket_sort.c %}


## 复杂度
### 时间复杂度
时间复杂度受桶因子影响，所以无法简单估计

### 空间复杂度
O(n)



# 计数排序

## 算法说明

计数排序是一种 **计数类** 的排序算法，是一种用空间换时间的算法


## 排序过程

1. 根据数据的最大值生成等量大小的桶
2. 遍历所有的数据并对值对应的桶计数
3. 遍历所有的桶并根据计数的还原数据

### 源代码

{% ghcode https://github.com/jipengzhu/dsa/blob/master/algorithm/sort/sort.h %}

{% ghcode https://github.com/jipengzhu/dsa/blob/master/algorithm/sort/series/count_sort.c %}


## 复杂度
### 时间复杂度
O(n)

### 空间复杂度
O(m)

> m 为数据中的最大值