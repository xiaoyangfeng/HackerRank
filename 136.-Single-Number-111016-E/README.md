# 136. Single Number
https://leetcode.com/problems/single-number/

Given an array of integers, every element appears twice except for one. Find that single one.

Note:  
Your algorithm should have a linear runtime complexity. Could you implement it without using extra memory?

```diff
+屌屌屌，又涨新姿势了
```
[猛戳](https://discuss.leetcode.com/topic/1916/my-o-n-solution-using-xor)


Yang's Solution
```java
public class Solution {
    public int singleNumber(int[] nums) {
        Arrays.sort(nums);
        for (int i = 1; i < nums.length - 1; i = i + 2) {

            if (nums[i] != nums[i - 1]) {
                return nums[i - 1];
            }
        }
        return nums[nums.length - 1];
    }
}
```
