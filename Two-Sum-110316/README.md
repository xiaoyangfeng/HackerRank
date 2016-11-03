# 1. Two Sum
https://leetcode.com/problems/two-sum/

Given an array of integers, return indices of the two numbers such that they add up to a specific target.

You may assume that each input would have exactly one solution.

Example:
```
Given nums = [2, 7, 11, 15], target = 9,

Because nums[0] + nums[1] = 2 + 7 = 9,
return [0, 1].
```
```diff
+UPDATE (2016/2/13):
```

The return format had been changed to zero-based indices. Please read the above updated description carefully.


--------------------------可以上传code below this line或者单独上传java------------------------------------------------

Yang's solution, 不清楚是不是还有更优的解法
```java
public class Solution {
    public int[] twoSum(int[] nums, int target) {
        for(int i=0;i<nums.length-1;i++){
            
            for (int j=i+1;j<nums.length;j++){
                if(nums[i]+nums[j]==target){
                    return new int[]{i,j};
                }
            }
        }
        return null;
    }
}
```
