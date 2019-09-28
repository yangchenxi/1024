# java刷题常用代码数据结构以及坑

## Hashmap:

```java
Hashmap<Integer,Integer> map=new HashMap<>()


```

## Treemap:

A Red-Black tree based NavigableMap implementation. The map is sorted according to the natural ordering of its keys, or by a Comparator provided at map creation time, depending on which constructor is used. This implementation provides guaranteed log(n) time cost for the containsKey, get, put and remove operations.

```java
    class TreeCompare implements Comparator<String> 
    { 
        /* Compares keys based on the  
           last word's natural ordering */
        public int compare(String a, String b) 
        { 
            
            return a.compareToIgnoreCase(b); 
         
        } 
          
    }

    TreeMap<String, Double> tm = new TreeMap<>(new TreeCompare()); 

    tm.containsKey(Object key);
    tm.containsValue(Object value);
    tm.fistKey();//return the lowest key currently in map
    tm.lastKey();//get the last key in sorted map
    tm.remove(Object key);
    


```



## PriorityQueue:

```java
//Default min heap, max heap is n2-n1
 PriorityQueue<Item> queue=new PriorityQueue<>((n1,n2)->{
            int count=n1.count-n2.count;
            return count;
            });


```

## Array:

```java
Arrays.fill(dp,0);


System.out.println(Arrays.toString(arr));

```

## ArrayList:

```java
List<String> messages = Arrays.asList("Hello", "World!", "How", "Are", "You");

```

## Collection:

```java
Collections.reverse(arraylist);
Collections.binarySearch(list,key);
Collections.singletonList(Obj);//return an immutable list containing only the specified object
Collections.sort(list,(p1, p2) -> p1.firstName.compareTo(p2.firstName));

```

## Union Find:

```java
  class UnionFind{
        public int parent[];
        int rank[];
        public UnionFind(int len){
            parent=new int[len];
            rank=new int[len];
            Arrays.fill(rank,0);
            for(int i=0;i<len;i++){
                parent[i]=i;
            }
        }
        public int Find(int index){//return the root index
            if(index==parent[index])return index;
            int parentIndex=Find(parent[index]);
            parent[index]=parentIndex;
            return parentIndex;
        }
        public void Union(int i1,int i2){
            int p1=Find(i1);
            int p2=Find(i2);
            if(p1==p2)return;
            if(rank[i1]==rank[i2]){
                parent[p2]=p1;
                rank[p1]++;
            }else if(rank[i1]>rank[i2]){
                parent[p2]=p1;
                rank[p1]++;
            }else if(rank[i1]<rank[i2]){
                parent[p1]=p2;
                rank[p2]++;
            }
        }       
}
```

复杂度:

Find( ): O(1)
Union( ): O(1)
Space: O(n)

## Quick Find:

**注意，quicksort这种partition的方法会打乱原来的relative order的顺序**

```java

```
## String/StringBuilder:


## BinaryTree:

### Inorder Traversal:

左->root->右


### Preorder Traversal:

root->左->右

### Postorder Traversal:

左->右->root

## Graph:

## BinaryOperations:

```
A XOR A = 0
```


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
7. Buy stock 问题是不用考虑底边长的，跟储水问题不一样
8. BFS DFS 注意成环问题,必要时用visited[]
9. StringBuilder 使用的时候记得每一层都用一个new







![](./art/coding.gif)
