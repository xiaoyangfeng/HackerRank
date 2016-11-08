# 419. Battleships in a Board
https://leetcode.com/problems/battleships-in-a-board/

Given an 2D board, count how many different battleships are in it. The battleships are represented with 'X's, empty slots are represented with '.'s. You may assume the following rules:

You receive a valid board, made of only battleships or empty slots.
Battleships can only be placed horizontally or vertically. In other words, they can only be made of the shape 1xN (1 row, N columns) or Nx1 (N rows, 1 column), where N can be of any size.
At least one horizontal or vertical cell separates between two battleships - there are no adjacent battleships.
Example:  
```java
X..X
...X
...X
```
In the above board there are 2 battleships.  
Invalid Example:  
```java
...X
XXXX
...X
```
This is an invalid board that you will not receive - as battleships will always have a cell separating between them.  
Follow up:   
Could you do it in one-pass, using only O(1) extra memory and without modifying the value of the board?

```diff
+感觉这是这几天的最简单M难度的题，还没看最优解
```
[最优解](https://discuss.leetcode.com/topic/62970/simple-java-solution/2)


Yang's solution
```java
public int countBattleships(char[][] board) {
        int rowNum = board.length;
        int columeNum = board[0].length;
        int result = 0;
        boolean[] columeBoolean = new boolean[columeNum];
        for (int i = 0; i < rowNum; i++) {
            boolean rowBoolean = false;
            for (int j = 0; j < columeNum; j++) {
                if(board[i][j] == '.'){
                    rowBoolean = false;
                    columeBoolean[j] = false;
                }else if (board[i][j] == 'X'&&!rowBoolean && !columeBoolean[j] ) {
                    result++;
                    rowBoolean = true;
                    columeBoolean[j] = true;
                } 
            }
        }
        return result;
    }
```
