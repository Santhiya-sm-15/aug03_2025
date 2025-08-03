# aug03_2025
The problem that i solved today 

You are given a 2D integer matrix mat[][] of size n × m and a list of q operations opr[][]. Each operation is represented as an array [v, r1, c1, r2, c2], where:

v is the value to be added
(r1, c1) is the top-left cell of a submatrix
(r2, c2) is the bottom-right cell of the submatrix (inclusive)
For each of the q operations, add v to every element in the submatrix from (r1, c1) to (r2, c2). Return the final matrix after applying all operations.

Code:
class Solution {
    public ArrayList<ArrayList<Integer>> applyDiff2D(int[][] mat, int[][] opr) {
        int n=mat.length;
        int m=mat[0].length;
        for(int[] x:opr)
        {
            int v=x[0],r1=x[1],c1=x[2],r2=x[3],c2=x[4];
            for(int i=r1;i<=r2;i++)
                for(int j=c1;j<=c2;j++)
                    mat[i][j]+=v;
        }
        ArrayList<ArrayList<Integer>> res=new ArrayList<>();
        for(int i=0;i<n;i++)
        {
            ArrayList<Integer> l=new ArrayList<>();
            for(int j=0;j<m;j++)
                l.add(mat[i][j]);
            res.add(l);
        }
        return res;
    }
}
