# Flood Fill
## https://leetcode.com/problems/flood-fill



# Implementation : DFS
```java
class Solution {
    public int[][] floodFill(int[][] image, int sr, int sc, int newColor) {
        if(newColor == image[sr][sc])
            return image;
        fill(image, sr, sc, image[sr][sc], newColor);
        return image;
    }
    
    private void fill(int[][] image, int i, int j, int oldColor, int newColor){
        if(i < 0 || i >= image.length || j < 0 || j >= image[i].length || image[i][j] != oldColor){
            return;
        }
        
        image[i][j] = newColor;
        fill(image, i, j+1, oldColor, newColor);
        fill(image, i, j-1, oldColor, newColor);
        fill(image, i+1, j, oldColor, newColor);
        fill(image, i-1, j, oldColor, newColor);
    }
}
```


# References :
1. https://www.youtube.com/watch?v=GRSy2cLxTxE
2. https://www.youtube.com/watch?v=TClRuEZ-uDg
