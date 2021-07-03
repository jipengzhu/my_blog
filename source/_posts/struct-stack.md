title: 栈的泛型实现c语言版
categories:
  - 编程
tags:
  - 算法
date: 2017-07-15 00:02:00
---
> 该栈是基于数组来实现的，并通过 `void*` 指针来实现泛型

> 该栈有大小限制，读者可以自行扩展，动态增大和减小数组

{% ghcode https://github.com/jipengzhu/dsa/blob/master/base/base.h %}

{% ghcode https://github.com/jipengzhu/dsa/blob/master/base/type/any_type.h {name:stack_type.h} %}

{% ghcode https://github.com/jipengzhu/dsa/blob/master/base/elem/stack_elem.h %}

{% ghcode https://github.com/jipengzhu/dsa/blob/master/struct/stack/stack.h %}

{% ghcode https://github.com/jipengzhu/dsa/blob/master/struct/stack/stack.c %}

{% ghcode https://github.com/jipengzhu/dsa/blob/master/struct/stack/generic_stack/main.c %}