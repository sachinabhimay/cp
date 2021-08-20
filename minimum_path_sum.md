Question: [Minimum path sum](https://leetcode.com/problems/minimum-path-sum/)

```
import java.lang.*;
class Solution {
    public int minPathSum(int[][] grid) {
        int row = grid.length;
        int col = grid[0].length;

        // how much it is to reach to end in first row of matix
        for(int i = 1; i < row; i ++){
            grid[i][0] += grid[i - 1][0];
        }
        
        // how much it is to reach to bottom of first column of matrix
        for(int j = 1; j < col; j++){
            grid[0][j] += grid[0][j-1];
        }
        
        // how to calculate for matrix of size 1 x 1 , 2 x 2 and so on
        for(int i = 1; i < row; i++){
            for(int j = 1; j < col; j ++){
                grid[i][j] = Math.min(grid[i - 1][j], grid[i][j - 1]) + grid[i][j];
            }
        }
        
        return grid[row - 1][col-1];
    }
}
```
