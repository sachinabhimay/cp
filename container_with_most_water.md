[Container with most water](https://leetcode.com/problems/container-with-most-water/)

```
import java.lang.*;
class Solution {

    public int maxArea(int[] height) {
        int h = height.length;
        int i, j, max = 0;
        // two pointers solution
        i = 0;
        j = h - 1;
        while(i < j){
        
            // keep moving from shorter side towards each other
            
            if (height[i] <= height[j]){
                max = Math.max(max, (j - i) * height[i]);
                i ++;
            }else{
                max = Math.max(max, (j - i) * height[j]);
                j--;
            }
        }
        return max;
    }
}
```

Time complexity : O(n)
Space complexity : O(1)
