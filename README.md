# dfs-leetcode-important-
1 Flood Fill
Input: 
image = [[1,1,1],[1,1,0],[1,0,1]]
sr = 1, sc = 1, newColor = 2
Output: [[2,2,2],[2,2,0],[2,0,1]]
class Solution {
public:
    void flood( vector<vector<int>>& image,int row,int col,int newColor,int oldColor)
    {
        if(row>=image.size() || row<0 || col>=image[0].size() || col<0 || image[row][col]!=oldColor)
        {
            return ;
        }
        image[row][col]=newColor;
         flood(image,row-1,col,newColor,oldColor);
         flood(image,row,col-1,newColor,oldColor);
         flood(image,row+1,col,newColor,oldColor);
         flood(image,row,col+1,newColor,oldColor);
    }
    vector<vector<int>> floodFill(vector<vector<int>>& image, int sr, int sc, int newColor) {
     
        if(newColor==image[sr][sc])
        {
            return image;
        }
        flood(image,sr,sc,newColor,image[sr][sc]);
        return image;
    }
};
