Given a word , rearrange the letters of  to construct another word  in such a way that  is lexicographically greater than . In case of multiple possible answers, find the lexicographically smallest one among them.

Input Format

The first line of input contains , the number of test cases. Each of the next  lines contains .

Constraints

 will contain only lower-case English letters and its length will not exceed .
Output Format

For each testcase, output a string lexicographically bigger than  in a separate line. In case of multiple possible answers, print the lexicographically smallest one, and if no answer exists, print no answer.

Sample Input

5  
ab  
bb  
hefg  
dhck  
dkhc  

Sample Output  

ba  
no answer  
hegf  
dhkc  
hcdk  
Explanation  

Test case 1:   
There exists only one string greater than ab which can be built by rearranging ab. That is ba.  
Test case 2:   
Not possible to rearrange bb and get a lexicographically greater string.  
Test case 3:   
hegf is the next string lexicographically greater than hefg.  
Test case 4:   
dhkc is the next string lexicographically greater than dhck.  
Test case 5:   
hcdk is the next string lexicographically greater than dkhc.  

```diff
-以下不是最优解，除去sort的部分，交换的部分是O(n2),最优解是2n
```

```java
 static String rearrangeWord(String word) {
        char[] letters = word.toCharArray();
        int length = letters.length;
        for (int i = length - 1; i > 0; i--) {
            for (int j = i - 1; j >= 0; j--) {
                if (letters[i] > letters[j]) {
                    char temp = letters[i];
                    letters[i] = letters[j];
                    letters[j] = temp;
                    Arrays.sort(letters, j + 1, length);
                    String result = String.valueOf(letters);

                    return result;
                }
            }
        }
        return "no answer";
    }

```
