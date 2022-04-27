## *Using Recursion:*

f(n) = f(n-1) + f(n-2)

## *Memoization*

int n=5;

  vector<int> dp(n+1,-1);
  
  dp[0]= 0;
  
  dp[1]= 1;
  
  for(int i=2; i<=n; i++){
                    
      dp[i] = dp[i-1]+ dp[i-2];
                    
  }
                    
  cout<<dp[n];
              
 
## *Tabulation*
              
int n=5;
  vector<int> dp(n+1,-1);
  
  dp[0]= 0;
  
  dp[1]= 1;
  
  
  for(int i=2; i<=n; i++){
                    
      dp[i] = dp[i-1]+ dp[i-2];
                    
  }
                    
  cout<<dp[n]; 

              
## *Space Optimization*
              
  int n=5;
  
  int prev2 = 0; 
              
  int prev = 1;
  
  for(int i=2; i<=n; i++){
  
      int cur_i = prev2+ prev;
  
      prev2 = prev;
  
      prev= cur_i;
  
  }
  
  cout<<prev;
