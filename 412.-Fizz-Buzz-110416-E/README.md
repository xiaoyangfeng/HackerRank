# 412. Fizz Buzz

https://leetcode.com/problems/fizz-buzz/

Write a program that outputs the string representation of numbers from 1 to n.

But for multiples of three it should output “Fizz” instead of the number and for the multiples of five output “Buzz”. For numbers which are multiples of both three and five output “FizzBuzz”.

Example:
```java
n = 15,

Return:
[
    "1",
    "2",
    "Fizz",
    "4",
    "Buzz",
    "Fizz",
    "7",
    "8",
    "Fizz",
    "Buzz",
    "11",
    "Fizz",
    "13",
    "14",
    "FizzBuzz"
]
```
```diff
+官方没有提供最优解！如果你得算法awesome，请share给大家~
```
Yang's solution
```java
public class Solution {
        public List<String> fizzBuzz(int n) {
        List<String> resultList = new ArrayList<>();
        for (int i = 1; i <= n; i++) {
            if (i % 15 == 0) {
                resultList.add("FizzBuzz");

            } else if (i % 3 == 0) {
                resultList.add("Fizz");

            } else if (i % 5 == 0) {
                resultList.add("Buzz");

            } else {
                resultList.add(String.valueOf(i));
            }
        }
        return resultList;
    }
}
```
