# 338. Counting Bits
https://leetcode.com/problems/counting-bits/

Given a non negative integer number num. For every numbers i in the range 0 ≤ i ≤ num calculate the number of 1's in their binary representation and return them as an array.

Example: 
```java
For num = 5 you should return [0,1,1,2,1,2].
```
Follow up:

It is very easy to come up with a solution with run time O(n*sizeof(integer)). But can you do it in linear time O(n) /possibly in a single pass?  
Space complexity should be O(n).  
Can you do it like a boss? Do it without using any builtin function like __builtin_popcount in c++ or in any other language.

Hint:  

You should make use of what you have produced already.

[非作弊最优解！！](https://discuss.leetcode.com/topic/40162/three-line-java-solution/2)


```diff
+我的作弊解法
```
```java
        public int[] countBits(int num) {
            int[] result=new int[num+1];
            for(int i=0;i<=num;i++){
            result[i]= Integer.bitCount(i);

            }
            return result;
       } 
```
