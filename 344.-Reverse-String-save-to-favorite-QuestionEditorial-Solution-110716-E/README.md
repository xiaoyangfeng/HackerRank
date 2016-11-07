# 344. Reverse String  

https://leetcode.com/problems/reverse-string/

Write a function that takes a string as input and returns the string reversed.

```java
Example:
Given s = "hello", return "olleh".
```

Yang's solution

```diff
+此题看似简单，实际暗藏玄机
```

```java
 public String reverseString(String s) {
        int l = s.length();
        char[] charArray = new char[l];
        for (int i = 0, j = l - 1; i < l; i++, j--) {
            charArray[i] = s.charAt(j);
        }
        return new String(charArray);
    }
```
