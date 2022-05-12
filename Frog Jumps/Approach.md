## Problem Statement:

Given a number of stairs and a frog, the frog wants to climb from the 0th stair to the (N-1)th stair. At a time the frog can climb either one or two steps. A height[N] array is also given. Whenever the frog jumps from a stair i to stair j, the energy consumed in the jump is abs(height[i]- height[j]), where abs() means the absolute difference. 
We need to return the minimum energy that can be used by the frog to jump from stair 0 to stair N-1.

### Link: https://www.codingninjas.com/codestudio/problems/frog-jump_3621012

## *Recursion*

*Why greedy not worked?*

As the problem statement states to find the minimum energy required, two approaches should come to our mind, greedy and dynamic programming.

First, we will see why a greedy approach will not work?

The total energy required by the frog depends upon the path taken by the frog. If the frog just takes the cheapest path in every stage it can happen that it eventually takes a costlier path after a certain number of jumps. The following example will help to understand this.

Step 1: Express the problem in terms of indexes

1 This can be easily done as there are array indexes [0,1,2,…, n-1].

2 We can say that f(n-1) signifies the minimum amount of energy required to move from stair 0 to stair n-1. 

3 Therefore f(0) simply should give us the answer as 0(base case).

Step 2: Try all the choices to reach the goal.

The frog can jump either by one step or by two steps. We will calculate the cost of the jump from the height array. The rest of the cost will be returned by the recursive calls that we make

Step 3: Take the minimum of all the choices

As the problem statement asks to find the minimum total energy, we will return the minimum of two choices of step2.

Also at ind=1, we can’t try the second choice so we will only make one recursive call.

The base case will be when we want to go to the 0th stair, then we have only one option.

<img width=350px height=300px src="https://user-images.githubusercontent.com/66131928/167454355-6070c19b-1dfc-43ef-9020-b66a07db2ba7.png"></img>

## *Memoization*

1. Create a dp[n] array initialized to -1.

2. Whenever we want to find the answer of a particular value (say n), we first check whether the answer is already calculated using the dp array(i.e dp[n] != -1 ). If yes, simply return the value from the dp array.

3. If not, then we are finding the answer for the given value for the first time, we will use the recursive relation as usual but before returning from the function, we will set dp[n] to the solution we get.

<img src=https://user-images.githubusercontent.com/66131928/168103875-f677b964-5c93-4035-8c71-5bcbafdea15c.png></img>
