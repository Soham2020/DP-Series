## Problem Statement

The frog was allowed to jump either one or two steps at a time. In this question, the frog is allowed to jump up to ‘K’ steps at a time. If K=4, the frog can jump 1,2,3, or 4 steps at every index.

## *Recursion*

We will first see the modifications required in the pseudo-code. Once the recursive code is formed, we can go ahead with the memoization and tabulation.

Here is the pseudocode from the simple Frog Jump problem.

<img width=390px src="https://user-images.githubusercontent.com/66131928/169557107-0ba0b2f1-3d33-4a38-94c7-8ee56d96dc36.png"></img>

This was the case where we needed to try two options (move a single step and move two steps) in order to try out all the possible ways for the problem. Now, we need to try K options in order to try out all possible ways.

These are the calls we need to make for K=2, K=3, K=4

<img height=300px src="https://user-images.githubusercontent.com/66131928/169557317-921b8ef5-3a37-46a0-86b4-1e3d9686d17e.png" ></img>

If we generalize, we are making K calls, therefore, we can set a for loop to run from 1 to K and in each iteration we can make a function call, corresponding to a step. We will return the minimum step call after the loop.

The final pseudo-code will be:

<img height=350px src="https://user-images.githubusercontent.com/66131928/169557736-7efc0532-81dd-40f9-9d19-162530ddb534.png"></img>

## *Memoization*

1. Create a dp[n] array initialized to -1.

2. Whenever we want to find the answer of a particular value (say n), we first check whether the answer is already calculated using the dp array(i.e dp[n] != -1 ). If yes, simply return the value from the dp array.

3. If not, then we are finding the answer for the given value for the first time, we will use the recursive relation as usual but before returning from the function, we will set dp[n] to the solution we get.
