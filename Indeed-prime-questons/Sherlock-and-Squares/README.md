# Sherlock and Squares

https://www.hackerrank.com/challenges/sherlock-and-squares

Watson gives two integers ( and ) to Sherlock and asks if he can count the number of square integers between  and  (both inclusive).

Note: A square integer is an integer which is the square of any integer. For example, 1, 4, 9, and 16 are some of the square integers as they are squares of 1, 2, 3, and 4, respectively.

Input Format

The first line contains , the number of test cases.  test cases follow, each in a new line. 
Each test case contains two space-separated integers denoting  and .

Constraints

 

Output Format

For each test case, print the required answer in a new line.

Sample Input
```
2
3 9
17 24
```
Sample Output
```
2
0
```
Explanation

Test Case #00: In range ,  and  are the two square numbers. 
Test Case #01: In range , there are no square numbers.

```diff
+上solution
```
```java
public static void main(String[] args) {
		// Enter your code here. Read input from STDIN. Print output to STDOUT.
		// Your class should be named Solution.
		Scanner in = new Scanner(System.in);
		in.next();
		while (in.hasNext()) {
			int a = in.nextInt();
			// System.out.println(a);
			int b = in.nextInt();
			// System.out.println(b);
			System.out.println((int) (Math.floor(Math.sqrt(b)) - Math.ceil(Math.sqrt(a))) + 1);
		}
	}
 ```
