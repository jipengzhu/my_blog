title: 二叉树的遍历c语言版
categories:
  - 编程
tags:
  - 算法
date: 2017-07-15 00:03:00
---
# 二叉树的遍历算法c语言版

[Github源代码](https://github.com/jipengzhu/dsa)


## 树的定义
树是一种数据结构，它是由n（n>=1）个有限结点组成一个具有层次关系的集合


## 树的特点
1. 每个结点有零个或多个`子结点`
2. 没有父结点的结点称为`根结点`
3. 非根结点有且只有一个`父结点`

> `父结点` 又称为 `双亲结点`


## 树的术语

|概念 | 定义
|--- |--- |
|子树 | 一个结点沿着从根到底的方向所能到达的所有节点组成的树称为`子树`
|双亲结点 | 若一个结点有子树，那么该结点称为子树`根结点`的`双亲`结点
|孩子结点 | 若一个结点有子树，那么子树`根结点`称为该结点的`孩子`结点
|后代结点 | 一个结点的所有子树上的任何结点都是该结点的`后代`结点
|祖先结点 | 根结点到某结点路径上的所有结点都是该结点的`祖先`结点
|结点的度 | 结点子树的个数称为`结点的度`
|树的度 | 最大的结点的度称为`树的度`
|叶子结点 | 没有任何子结点的结点称为`叶子`结点，或者度为0的结点
|分支结点 | 至少有一个子结点的结点称为`分支`结点，或者度不为0的结点



## 二叉树的定义
二叉树是指每个结点最多有两个子树的树结构

它有五种基本形态：二叉树可以是空集；可以有空的左子树或右子树；或者左、右子树都为空;或者左、右子树都不为空


## 二叉树的性质
1. 二叉树第j层上的结点数目至多为2<sup>j-1</sup> (j>=1)
2. 深度为k的二叉树至多有2<sup>k</sup>-1个结点 (k>=1)
3. 若某结点的编号为i，则该结点的左子结点的编号为2 * i
4. 若某结点的编号为i，则该结点的右子结点的编号为2 * i + 1
5. 若度为0结点个数为n0，度为2的结点数为n2，则 n0 = n2 + 1

## 度公式的证明
定理：度实际是连接结点的边，所以结点的个数等于度的总数加1
证明：
因为二叉树中所有结点的度数均不大于2，不妨设n0表示度为0的结点个数，n1表示度为1的结点个数，n2表示度为2的结点个数，于是便可得到结点的总数：`n = n0 + n1 + n2(1)` 
由于边（也是度）的大小为结点的个数减一， 所以由度和结点的关系可得到结点的总数：`n = n0 * 0 + n1 * 1 + n2 * 2 + 1`，即 `n = n1 + 2 * n2 + 1(2)`
将（1）（2）组合在一起可得到 `n0 = n2 + 1`

## 满二叉树、完全二叉树和二叉查找树
### 满二叉树
定义：在一棵二叉树中，如果所有的分支结点都有左子树和右子树，并且所有叶子结点都在同一层上，这样的二叉树称为满二叉树

### 完全二叉树
定义：在一棵二叉树中，不存在有右结点但无左结点的情况，并且所有叶子结点的层次差别不超过一，这样的二叉树称为完全二叉树

> 显然，一棵满二叉树必定是一棵完全二叉树，而完全二叉树未必是满二叉树

### 二叉查找树
定义：二叉查找树又被称为二叉搜索树

设x为二叉查找树中的一个结点，x结点包含关键字key，结点x关于key的值记为key[x]

如果y是x的左子树中的一个结点，则key[y] < key[x]
如果y是x的右子树中的一个结点，则key[y] > key[x]


特点：
（1）若任意结点的左子树不空，则左子树上所有结点的值均小于它的根结点的值
（2）若任意结点的右子树不空，则右子树上所有结点的值均大于它的根结点的值
（3）任意结点的左、右子树也分别为二叉查找树

## 二叉树的遍历顺序
### 深度优先遍历
#### 先序遍历
先访问父结点，然后访问左子树，最后访问右子树

#### 中序遍历
先访问左子树，然后访问父结点，最后访问右子树

#### 先序遍历
先访问左子树，然后访问右子树，最后访问父结点

### 广度优先遍历
先访问结点以及该结点的兄弟结点，再访问子结点

> 广度优先遍历需要队列来记录已经访问过的结点以便访问该结点的子结点

## 二叉树的遍历（递归实现）
> 编译命令如下

`gcc main.c`

效果如下（按先序遍历顺序输入，＃用来指示该结点无子结点，两个#表示该结点无左右子结点）：

<pre>
➜  tree_traversal git:(master) gcc queue.c tree_traversal_recursive.c
➜  tree_traversal git:(master) ✗ ./a.out
please input abcd###e##f#gh### and press enter or return key
abcd###e##f#gh###

the tree depth is 4
the tree is
      a
     / \
    b   f
   / \   \
  c   e   g
 /       /
d       h

pre order traversal
a	b	c	d	e	f	g	h
mid order traversal
d	c	b	e	a	f	h	g
post order traversal
d	c	e	b	h	g	f	a
level order traversal
a	b	f	c	e	g	d	h
</pre>

源码如下，树的构造按照先序遍历构造
(队列和栈的部分参照{% post_link struct-queue 队列%}和{% post_link struct-stack 栈 %})

{% ghcode https://github.com/jipengzhu/dsa/blob/master/base/elem/tree_elem.h %}

{% ghcode https://github.com/jipengzhu/dsa/blob/master/struct/tree/tree.h %}

{% ghcode https://github.com/jipengzhu/dsa/blob/master/struct/tree/traversal_recursive/tree.c %}

{% ghcode https://github.com/jipengzhu/dsa/blob/master/struct/tree/help.c %}

{% ghcode https://github.com/jipengzhu/dsa/blob/master/struct/tree/main.c %}


## 二叉树的遍历（栈实现）

> 编译命令如下

`gcc main.c`

效果如下（按先序遍历顺序输入，＃用来指示该结点无子结点，两个#表示该结点无左右子结点）：

<pre>
➜  tree_traversal git:(master) ✗ gcc queue.c stack.c tree_traversal_stack.c
➜  tree_traversal git:(master) ✗ ./a.out
please input abcd###e##f#gh### and press enter or return key
abcd###e##f#gh###

the tree depth is 4
the tree is
      a
     / \
    b   f
   / \   \
  c   e   g
 /       /
d       h

pre order traversal
a	b	c	d	e	f	g	h
mid order traversal
d	c	b	e	a	f	h	g
post order traversal
d	c	e	b	h	g	f	a
level order traversal
a	b	f	c	e	g	d	h
</pre>

源码如下，树的构造按照先序遍历构造
(队列和栈的部分参照{% post_link struct-queue 队列%}和{% post_link struct-stack 栈 %})

{% ghcode https://github.com/jipengzhu/dsa/blob/master/base/elem/tree_elem.h %}

{% ghcode https://github.com/jipengzhu/dsa/blob/master/struct/tree/tree.h %}

{% ghcode https://github.com/jipengzhu/dsa/blob/master/struct/tree/traversal_stack/tree.c %}

{% ghcode https://github.com/jipengzhu/dsa/blob/master/struct/tree/help.c %}

{% ghcode https://github.com/jipengzhu/dsa/blob/master/struct/tree/main.c %}



---

# 参考

[二叉树基础知识总结][1]

[1]: (http://blog.csdn.net/xiaoquantouer/article/details/65631708)