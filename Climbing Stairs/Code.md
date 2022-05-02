## *Recursion:*

```
f(ind) {

  if(ind == 0 || ind == 1)  return 1;

  return f(ind-1) + f(ind+1);

}
```

## *Tabulation*

```
int n=3;
vector<int> dp(n+1,-1);
  
dp[0]= 1;
dp[1]= 1;
  
for(int i=2; i<=n; i++){
    dp[i] = dp[i-1]+ dp[i-2];
}
cout<<dp[n];  
```
