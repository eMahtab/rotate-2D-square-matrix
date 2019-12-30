# Rotate 2D Square Matrix

### Implementation :

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
