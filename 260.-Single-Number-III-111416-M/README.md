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
