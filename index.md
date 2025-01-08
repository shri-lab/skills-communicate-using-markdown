```
import java.util.*;
public class sortedmatrix {
    public static void main(String[] args) {
        int[][] matrix = {
                {1,2,3,4,5},
                {6,7},
                {8,9,10,11,12}
        };
        System.out.println(Arrays.toString(search(matrix, 7)));
    }

    // search in the row provided between the cols provided
    static int[] binarySearch(int[][] matrix, int rw, int end, int target) {
 int start = 0;
        while(start <= end) {
           int mid = start + (end - start) / 2;

            if (target < matrix[rw][mid]) {
                end = mid - 1;
            } else if (target > matrix[rw][mid]) {
                start = mid + 1;
            } else {
                // ans found
                return new int[]{rw,mid};
            }
        }
        return new int[]{-1,-1};
    }
    static int[] search(int[][] matrix, int target) {
        int i =0;
        int j = matrix[i].length - 1;
        int m = matrix.length;

        while(i!=m)
        {
            j = matrix[i].length - 1;
            if(j==-1)
            {
                i++;
                continue;
            }
           if(matrix[i][j]>target)
           {
           return binarySearch(matrix , i ,j,target );
           }
           else if(matrix[i][j]<target)
           {
            i++;
           }
           else
           {
            return new int[]{i,j};
           }
    }
        return new int[]{-1,-1};
}}
```
- [ ] Turn on GitHub Pages
- [ ] Outline my portfolio
- [ ] Introduce myself to the world
