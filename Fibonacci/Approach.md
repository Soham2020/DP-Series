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
This technique is called Memoization. Here the cases marked in yellow are called overlapping sub-problems and we need to solve them only once during the code execution.<br/>
