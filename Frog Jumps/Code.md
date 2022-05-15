## *Recursion*

```

int solve(int ind, vector<int>& height){
    if(ind==0) return 0;
    int jumpTwo = INT_MAX;
    int jumpOne= solve(ind-1, height,dp)+ abs(height[ind]-height[ind-1]);
    if(ind>1)
        jumpTwo = solve(ind-2, height,dp)+ abs(height[ind]-height[ind-2]);
    
    return min(jumpOne, jumpTwo);
}
  
```
