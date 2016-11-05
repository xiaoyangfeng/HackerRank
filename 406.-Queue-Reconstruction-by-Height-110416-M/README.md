# 406. Queue Reconstruction by Height   QuestionEditorial Solution

https://leetcode.com/problems/queue-reconstruction-by-height/

Suppose you have a random list of people standing in a queue. Each person is described by a pair of integers (h, k), where h is the height of the person and k is the number of people in front of this person who have a height greater than or equal to h. Write an algorithm to reconstruct the queue.

Note:  
The number of people is less than 1,100.
```java
Example

Input:
[[7,0], [4,4], [7,1], [5,0], [6,1], [5,2]]

Output:
[[5,0], [7,0], [5,2], [6,1], [4,4], [7,1]]
```
```diff
+Yang's solution
+请注意此方法通不过大量数据的时间限制 233333333333333
```

```java
public class Solution {
public static int[][] reconstructQueue(int[][] people) {
        LinkedList<int[]> list = new LinkedList<>(Arrays.asList(people));
        int j = 1;
        boolean insert = false;

        for (int i = 0; i < list.size() - 1;) {
            if (list.get(i)[0] > list.get(j)[0] || list.get(i)[0] == list.get(j)[0] && list.get(i)[1] < list.get(j)[1]) {
                if (insert) {
                    list.add(j - 1, list.remove(i));
                    j=i+1;
                    insert = false;
                    continue;
                }
                if (j == list.size() - 1) {
                    i++;
                    j=i+1;
                    continue;
                }
                j++;

            } else {
                insert = true;
                if (j == list.size() - 1) {
                    list.addLast(list.remove(i));
                    j = i + 1;
                    insert = false;
                    continue;
                }
                j++;
            }
        }
        for (int i = 1; i < list.size(); i++) {
            int point = list.get(i)[1];
            if (point != i) {
                list.add(point, list.remove(i));
            }
        }
        return list.toArray(new int[0][0]);

    }
}
```
