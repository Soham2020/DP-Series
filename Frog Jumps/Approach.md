## Problem Statement:

Given a number of stairs and a frog, the frog wants to climb from the 0th stair to the (N-1)th stair. At a time the frog can climb either one or two steps. A height[N] array is also given. Whenever the frog jumps from a stair i to stair j, the energy consumed in the jump is abs(height[i]- height[j]), where abs() means the absolute difference. 
We need to return the minimum energy that can be used by the frog to jump from stair 0 to stair N-1.

### Link: https://www.codingninjas.com/codestudio/problems/frog-jump_3621012

## *Recursion*

*Why greedy not worked?*

As the problem statement states to find the minimum energy required, two approaches should come to our mind, greedy and dynamic programming.

First, we will see why a greedy approach will not work?

The total energy required by the frog depends upon the path taken by the frog. If the frog just takes the cheapest path in every stage it can happen that it eventually takes a costlier path after a certain number of jumps. The following example will help to understand this.
