# Problem Statement
### `We need to find the nth Fibonacci number, where n is based on a 0-based index.`

***Hint:*** Every `ith` number of the series is equal to the sum of `(i-1)th` and `(i-2)th` number where the first and second number is given as 0 and 1 respectively.

## Link: 

## Approaches:

### ***Recursive way***

As every number is equal to the sum of the previous two terms, the recurrence relation can be written as:

<img src="https://user-images.githubusercontent.com/66131928/164275819-a5e9a963-6185-4dbb-abb9-3c9b16ebf3e4.png"></img>

The basic pseudo-code for the problem will be given as:

<img src="https://lh5.googleusercontent.com/UK4N8ZsaDe1E50UvVoW5QMGpHztH6dHArb8pAQ-prDBSz5ZYAYCYgavuAZXny9WbD1eZOtGNf5_tYo3rmM3TcB5RKKTeWeZ1is1mrSkwr1UbiXfP830F8Y-mkN0Zo5WyyClpTUOe"></img>

If we draw the recursive tree for n=5, it will be:

<img src="https://user-images.githubusercontent.com/66131928/164276338-5f5f874a-d327-4f20-9fdd-b79dd6b6439f.png"></img>

If there are two recursive calls inside a function, the program will run the first call, finish its execution and then run the second call. Due to this reason, each and every call in the recursive tree will be executed. This gives the recursive code its exponential time complexity.
Can we improve on this? The answer is `Yes!`

<img src="https://user-images.githubusercontent.com/66131928/164276646-c31ed188-15c3-4998-af2a-4d21057c0e26.png"></img>

We want to compute *f(2)* as the second call from *f(4)*, but in the recursive tree we had already computed *f(2)* once (in the first recursive call of *f(3)* ).<br/>
Similar is the case with *f(3)*, therefore if we somehow store these values, the first time we calculated it then we can simply find its value in constant time whenever we need it.<br/> 
This technique is called ***Memoization***. Here the cases marked in yellow are called overlapping sub-problems and we need to solve them only once during the code execution.<br/>

### ***Memoization:***

Any recursive solution to a problem can be memoized using these three steps:

1. Create a *dp[n+1]* array initialized to *-1*.
2. Whenever we want to find the answer of a particular value (say n), we first check whether the answer is already calculated using the dp array(i.e *dp[n]!= -1* ). If yes, simply return the value from the dp array.
3. If not, then we are finding the answer for the given value for the first time, we will use the recursive relation as usual but before returning from the function, we will set *dp[n]* to the solution we get.

***Dry Run***:

Declare a dp[] array of size n+1 and initialize it to -1.

<img src="https://user-images.githubusercontent.com/66131928/164508507-1099b75d-da84-4f50-acf4-699f25541323.png"></img>

Now, following the recursive code we see that at n=5, the value of dp[5] is equal to -1 therefore we need to compute its value and go to the inner recursive calls. Similar is the case at n=4, n=3, and n=2. For n=2, we hit our two base conditions as the inner recursive calls.

As we traverse back after solving n=2, we update its dp array value to 1 ( the answer we got). Similarly, for the second recursive call for n=3, we again hit a base condition and we get an answer of f(n=3) as 2, we again update the dp array.

<img src="https://user-images.githubusercontent.com/66131928/164508763-4d2d7289-33b7-4881-99f0-583bf54c14e2.png"></img>

Then for the second recursive call f(n=4), we see that dp[2] is not equal to -1, which means that we have already solved this subproblem and we simply return the value at dp[2] as our answer. Hence we get the answer of f(n=4) as 3(2+1).

Similarly, for the second recursive call f(n=5), we get dp[3] as 2. Then we compute for(n=5) as 5(2+3).

<img src="https://user-images.githubusercontent.com/66131928/164508895-86747040-6572-4b53-aaf3-880796d1d3cd.png"></img>
