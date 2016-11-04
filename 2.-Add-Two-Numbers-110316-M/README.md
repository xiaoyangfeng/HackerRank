# 2. Add Two Numbers
https://leetcode.com/problems/add-two-numbers/


You are given two linked lists representing two non-negative numbers. The digits are stored in reverse order and each of their nodes contain a single digit. Add the two numbers and return it as a linked list.

```
Input: (2 -> 4 -> 3) + (5 -> 6 -> 4)
Output: 7 -> 0 -> 8
```


.......................................................................................................................
Yang's solution(！！！！！此解法只适用于数值在int范围之内的，稍后更新string解法！！！！！)
```java
/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode(int x) { val = x; }
 * }
 */
public class Solution {
    public ListNode addTwoNumbers(ListNode l1, ListNode l2) {
        int num1=0;
         int count1=0;
         while(l1!=null){
            num1+= l1.val*Math.pow(10, count1);
            l1=l1.next;
            count1++;
        }
        int num2=0;
         int count2=0;
         while(l2!=null){
            num2+= l2.val*Math.pow(10, count2);
            l2=l2.next;
            count2++;
        }
       int sum=num1+num2;
        ListNode result=new ListNode(sum%10);
        sum=sum/10;
        if(sum==0){
            return result;
        }
        result.next=new ListNode(0);
        ListNode pointer=result.next;
        while(sum!=0){
           pointer.val=sum%10;
            sum=sum/10;
             if(sum==0){
                 break;
            }
            pointer.next=new ListNode(0);
            pointer=pointer.next;
        }
        return result; 
    }
}
```
