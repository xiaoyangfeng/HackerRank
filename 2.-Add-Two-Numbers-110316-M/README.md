# 2. Add Two Numbers
https://leetcode.com/problems/add-two-numbers/


You are given two linked lists representing two non-negative numbers. The digits are stored in reverse order and each of their nodes contain a single digit. Add the two numbers and return it as a linked list.

```
Input: (2 -> 4 -> 3) + (5 -> 6 -> 4)
Output: 7 -> 0 -> 8
```


.......................................................................................................................   

[猛戳最优解，我的解法简直不能直视](https://leetcode.com/articles/add-two-numbers/)

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

String解法

```java
public class Solution {
    public ListNode addTwoNumbers(ListNode l1, ListNode l2) {
         String string1="";
         while(l1!=null){
            string1+= l1.val;
            l1=l1.next;
        }
         String string2="";
         while(l2!=null){
            string2+= l2.val;
            l2=l2.next;
        }
        int length1=string1.length();
        int length2=string2.length();
        int max=length1;
        if (length1<length2){
            max=length2;
        }
        int num1=0;
        int num2=0;
        int rest=0;
        int sum=0;
        num1=Integer.parseInt(string1.substring(0, 1));
        num2=Integer.parseInt(string2.substring(0, 1));
        sum=num1+num2;
        
        ListNode result=new ListNode(sum%10);
        rest=sum/10;
        if(rest==0&&length1==1&&length2==1){
            return result;
        }
        result.next=new ListNode(0);
        ListNode pointer=result.next;
        
        for(int i=1;i<=max;i++){
            if(i<length1){
                num1=Integer.parseInt(string1.substring(i, i+1));
            }else{
                num1=0;
            }
            if(i<length2){
                num2=Integer.parseInt(string2.substring(i, i+1));
            }else{
                num2=0;
            }
            sum=num1+num2+rest;
            pointer.val=sum%10;
            rest=sum/10;
            if(rest==0&&i>=max-1){
                 break;
            }
            pointer.next=new ListNode(0);
            pointer=pointer.next;
        }
        return result; 
    }
}
```

