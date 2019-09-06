# java刷题常用代码数据结构以及坑

## Hashmap:

```java
Hashmap<Integer,Integer> map=new HashMap<>()


```

## Treemap:

```java

```

## PriorityQueue:

```java

```

## Array:

```java

```

## ArrayList:

```java

```

## Collection:

```java

```

## Union Find:

```java

```

## Quick Find:

**注意，quicksort这种partition的方法会打乱原来的relative order的顺序**

```java

```
## String/StringBuilder:


## BinaryTree:

### Inorder Traversal:

左->root->右

Iterative 的方法：
https://leetcode.com/problems/binary-tree-inorder-traversal

## Preorder Traversal:




## 常识：

### 闰年规则：

### IP地址规则：

for a segment:

1. less or equal to 255
2. the first character could be '0' only if the segment is equal to '0'

e.g. "010010" should not be interpreted as 01,00,1,0

# 打代码时候必须注意的坑：

1. 注意区分array中的index和value，别用混
2. 注意Integer和String这种Object比较时候用 .intValue() .equals()
3. binary search或者涉及到sliding window，two pointer 的题注意事先写好开闭区间
4. 涉及到Integer的问题一定注意Overflow的问题！如果可以的话用Long
5. 涉及到字符串的问题一定要考虑到有重复字母的testcase
6. Linkedlist 注意check null，fakehead必要时引入







![](./art/coding.gif)