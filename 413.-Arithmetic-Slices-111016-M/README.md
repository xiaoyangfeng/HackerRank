# 413. Arithmetic Slices
https://leetcode.com/problems/arithmetic-slices/

A sequence of number is called arithmetic if it consists of at least three elements and if the difference between any two consecutive elements is the same.

For example, these are arithmetic sequence:
```
1, 3, 5, 7, 9
7, 7, 7, 7
3, -1, -5, -9
```
The following sequence is not arithmetic.
```
1, 1, 2, 5, 7
```
A zero-indexed array A consisting of N numbers is given. A slice of that array is any pair of integers (P, Q) such that 0 <= P < Q < N.

A slice (P, Q) of array A is called arithmetic if the sequence:  
A[P], A[p + 1], ..., A[Q - 1], A[Q] is arithmetic. In particular, this means that P + 1 < Q.

The function should return the number of arithmetic slices in the array A.


Example:
```
A = [1, 2, 3, 4]

return: 3, for 3 arithmetic slices in A: [1, 2, 3], [2, 3, 4] and [1, 2, 3, 4] itself.
```
[最优解依然牛B！](https://discuss.leetcode.com/topic/63302/simple-java-solution-9-lines-2ms/2)


Yang's solution
```java
    public int numberOfArithmeticSlices(int[] A) {
        int result = 0;
        int diff = 0;
        int count = 1;
        for (int i = 1; i < A.length; i++) {
            if (A[i] - A[i - 1] != diff) {
                if (count >= 3) {
                    int n = count - 2;
                    result += n * (n + 1) / 2;
                }
                diff = A[i] - A[i - 1];
                count = 2;
            } else {
                count++;
            }
        }
        if (count >= 3) {
            int n = count - 2;
            result += n * (n + 1) / 2;
        }
        return result;
    }
```
