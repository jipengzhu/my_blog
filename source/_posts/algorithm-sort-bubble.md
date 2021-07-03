title: 排序算法之冒泡排序c语言版
categories:
  - 编程
tags:
  - 算法
date: 2017-07-15 00:05:00
---
# 算法说明

冒泡排序是一种 **交换类** 的排序算法，也是一种比较直观和容易理解的算法


## 冒泡过程

1. 对`未排序部分`的元素`自后向前`进行相邻比较，如果后面的小，则进行交换
2. 经过一趟排序后，`最小`的元素就出现在了`最前面`，这个过程称为`冒泡过程`

然后再对剩下的`未排序部分`的元素重复此过程，直到整个列表有序

### 源代码

{% ghcode https://github.com/jipengzhu/dsa/blob/master/algorithm/sort/sort.h %}

{% ghcode https://github.com/jipengzhu/dsa/blob/master/algorithm/sort/bubble/bubble_sort_rise.c %}


## 下沉过程

1. 对`未排序部分`的元素`自前向后`进行相邻比较，如果前面的大，则进行交换
2. 经过一趟排序后，`最大`的元素就出现在了`最后面`，这个过程称为`下沉过程`

然后再对剩下的`未排序部分`的元素重复此过程，直到整个列表有序

### 源代码

{% ghcode https://github.com/jipengzhu/dsa/blob/master/algorithm/sort/sort.h %}

{% ghcode https://github.com/jipengzhu/dsa/blob/master/algorithm/sort/bubble/bubble_sort_sink.c%}


## 复杂度
### 时间复杂度
O(n<sup>2</sup>)

### 空间复杂度
O(1)



# 排序优化

在比较过程中，如果前面的部分（冒泡过程）或者后面的部分（下沉过程）没有出现一次需要交换的情况，则说明这部分本身就是有序的，否则就会因为大小比较而发生交换过程

所以我们可以记录最后一次发生交换时的位置，则这个位置的前面部分（冒泡过程）或者后面部分（下沉过程）因为本身已经有序，在下一次的比较过程中就无须再进行比较


## 冒泡过程

### 源代码

{% ghcode https://github.com/jipengzhu/dsa/blob/master/algorithm/sort/sort.h %}

{% ghcode https://github.com/jipengzhu/dsa/blob/master/algorithm/sort/bubble/bubble_sort_flag_rise.c %}

> 注意pos的初始值为 n - 1


## 下沉过程

### 源代码

{% ghcode https://github.com/jipengzhu/dsa/blob/master/algorithm/sort/sort.h %}

{% ghcode https://github.com/jipengzhu/dsa/blob/master/algorithm/sort/bubble/bubble_sort_flag_sink.c %}

> 注意pos的初始值为 0


## 复杂度
### 时间复杂度
O(n<sup>2</sup>)

### 空间复杂度
O(1)