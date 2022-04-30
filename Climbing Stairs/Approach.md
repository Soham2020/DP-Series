## Problem Statement: 
`Given a number of stairs. Starting from the 0th stair we need to climb to the “Nth” stair. At a time we can climb either one or two steps. We need to return the total number of distinct ways to reach from 0th to Nth stair.`

## Link:

## Recursion:

<img width=400px height=350px src = "https://user-images.githubusercontent.com/66131928/165974698-98b90063-b79f-4b87-a1e6-c9282272eecf.png"></img>

## Tabulation:

Steps for the Tabulation approach.

1. Declare a dp[] array of size n+1.
2. First initialize the base condition values, i.e i=0 and i=1 of the dp array as 1.
3. Set an iterative loop which traverses the array( from index 2 to n) and for every index set its value as dp[i-1] + dp[i-2]. 
