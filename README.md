# Rotate 2D Square Matrix

You are given an n x n 2D matrix representing an image.

Rotate the image by 90 degrees (clockwise).

**Note: You have to rotate the image in-place, which means you have to modify the input 2D matrix directly. DO NOT allocate another 2D matrix and do the rotation.**

```
Example 1:

Given input matrix = 
[
  [1,2,3],
  [4,5,6],
  [7,8,9]
],

rotate the input matrix in-place such that it becomes:
[
  [7,4,1],
  [8,5,2],
  [9,6,3]
]
```
```
Example 2:

Given input matrix =
[
  [ 5, 1, 9,11],
  [ 2, 4, 8,10],
  [13, 3, 6, 7],
  [15,14,12,16]
], 

rotate the input matrix in-place such that it becomes:
[
  [15,13, 2, 5],
  [14, 3, 4, 1],
  [12, 6, 8, 9],
  [16, 7,10,11]
]
```

### Implementation 

```java
import java.util.Arrays;

public class App {

	public static void main(String[] args) {
		int[][] mat = { { 1, 2, 3 }, 
				{ 4, 5, 6 }, 
				{ 7, 8, 9 } 
			      };

		rotate(mat);
		for (int[] row : mat) {
			System.out.println(Arrays.toString(row));
		}
	}

	public static void rotate(int[][] a) {
		   transpose(a);
		   reverseRow(a);
	}

	private static void reverseRow(int[][] a) {
		int n = a.length;
		for(int i = 0; i < n; i++) {
			int start = 0;
			int last = n-1;
			while(start < last) {
				int temp = a[i][start];
				a[i][start] = a[i][last];
				a[i][last] = temp;
				start++;
				last--;
			}
		}
	}

	private static void transpose(int[][] a) {
		int n = a.length;
		for (int i = 0; i < n; i++) {
			for (int j = i; j < n; j++) {
				int temp = a[i][j];
				a[i][j] = a[j][i];
				a[j][i] = temp;
			}
		}

	}
}

```
The above implementation have Runtime complexity of O(n^2) and space complexity of O(1)
```
Runtime Complexity = O(n^2)
Space Complexity   = O(1)
```
