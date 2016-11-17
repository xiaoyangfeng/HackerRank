# super stack
http://java4programming.blogspot.com/2015/04/1st-try.html

Requirements:
- Print value of "peak" after each operation.
- n            : the number of operations
- POP       : get the value of "peak", if there is no more value after pop, then print "EMPTY"
- PUSH d : put the new value(d) after "peak", then print the value of "peak"
- INC x d : add the new value(d) from index 0 to x elements, then print the value of "peak"

- Example
  input   :
               8
               PUSH 1
               POP
               PUSH 3
               PUSH 4
               PUSH 5
               INC 3 1
               POP
               PUSH 9
  output :
               1
               EMPTY
               3
               4
               5
               6
               4
               9

 the values in the Super Stack
 peak       9
               5
 base       4
 
 [答案in C#](https://www.snip2code.com/Snippet/357517/HackerRank-Super-Stack-Solution)
