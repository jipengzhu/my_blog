title: 队列的泛型实现c语言版
author: 朱继鹏
tags:
  - 算法
categories:
  - ''
  - 编程
date: 2017-07-15 00:01:00
---
> 该队列是基于数组来实现的，并通过 `void*` 指针来实现泛型

> 该队列有大小限制，读者可以自行扩展，动态增大和减小数组

{% ghcode https://github.com/jipengzhu/dsa/blob/master/base/base.h %}

{% ghcode https://github.com/jipengzhu/dsa/blob/master/base/type/any_type.h {name:queue_type.h} %}

{% ghcode https://github.com/jipengzhu/dsa/blob/master/base/elem/queue_elem.h %}

{% ghcode https://github.com/jipengzhu/dsa/blob/master/struct/queue/queue.h %}

{% ghcode https://github.com/jipengzhu/dsa/blob/master/struct/queue/queue.c %}

{% ghcode https://github.com/jipengzhu/dsa/blob/master/struct/queue/generic_queue/main.c %}