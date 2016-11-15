# 260. Single Number III
https://leetcode.com/problems/single-number-iii/

Given an array of numbers nums, in which exactly two elements appear only once and all the other elements appear exactly twice. Find the two elements that appear only once.

For example:
```
Given nums = [1, 2, 1, 3, 2, 5], return [3, 5].
```
Note:  
The order of the result is not important. So in the above example, [5, 3] is also correct.  
Your algorithm should run in linear runtime complexity. Could you implement it using only constant space complexity?
```diff
+最优解不太好理解
+一旦你理解了，你对二进制的运算会更上一层楼
```
[看来本科计算机的基础教育还是很有必要的](https://discuss.leetcode.com/topic/21605/accepted-c-java-o-n-time-o-1-space-easy-solution-with-detail-explanations/2)



Yang's solution

```java
        public int[] singleNumber(int[] nums) {
    Arrays.sort(nums);
    int[] result=new int[2];
    int count=0;
    int index=nums.length-1;
        for(int i=0;i<index;i=i+2){
            if(count==2){
                return result;
            }
            if(nums[i]!=nums[i+1]){
                result[count]=nums[i];
                count++;
                i--;
            }
        }
        if(count==1){
           result[1]=nums[index];
        }
        return result;
    }
```
