# Activities

## Task 1

Refer to the following link. Explain how the Knapsack Algorithm works:
https://monicagranbois.com/knapsack-algorithm-visualization/

The Knapsack Algorithm is a dynamic programming algorithm that solves the classic Knapsack problem. The Knapsack problem is a combinatorial optimization problem in which a set of items, each with a weight and a value, must be selected and placed into a knapsack with a limited capacity, such that the total value of the items placed in the knapsack is maximized.

The Knapsack Algorithm works by building a table that represents the optimal value that can be achieved for each possible combination of items and capacities. The table is filled in a bottom-up manner, starting with the base case where the capacity is 0 and no items can be placed in the knapsack. For each subsequent capacity, the algorithm considers adding each of the items to the knapsack and chooses the item with the maximum value-to-weight ratio that can be added without exceeding the capacity.

The algorithm takes as input the weights and values of the items, as well as the capacity of the knapsack. It returns the maximum value that can be achieved by placing a subset of the items into the knapsack.

Here is a high-level overview of the Knapsack Algorithm:

    Initialize a table with (n+1) rows and (W+1) columns, where n is the number of items and W is the capacity of the knapsack.
    Initialize the first row and column of the table to 0, since the maximum value that can be achieved with 0 capacity or 0 items is 0.
    For each item i from 1 to n, and for each capacity w from 1 to W:
    a. If the weight of the current item is greater than the current capacity w, then the maximum value that can be achieved is the same as the maximum value that can be achieved without the current item: table[i-1][w].
    b. Otherwise, the maximum value that can be achieved is the maximum of:
    i. The maximum value that can be achieved without the current item: table[i-1][w]
    ii. The value of the current item plus the maximum value that can be achieved with the remaining capacity after adding the current item: table[i-1][w-w[i]] + v[i]
    Return the maximum value that can be achieved, which is stored in the last cell of the table: table[n][W].


## Task 2

Refer to the following link. What are the difference between the brute force and the optimized solutions to the Knapsack problem.
https://www.educative.io/blog/0-1-knapsack-problem-dynamic-solution

The Knapsack problem is an optimization problem in which we are given a set of items, each with a weight and a value, and a knapsack with a capacity, and we need to maximize the total value of items that can be put into the knapsack without exceeding its capacity.

The brute force approach to solve the Knapsack problem is to generate all possible combinations of items that can be put into the knapsack and calculate their total value, and then choose the combination with the maximum value that fits within the knapsack's capacity. The time complexity of this approach is exponential, which means that it's not practical for large inputs.

The optimized solutions to the Knapsack problem use various algorithms that are more efficient than the brute force approach. One of the most popular algorithms is the dynamic programming approach. In this approach, we create a two-dimensional array to store the maximum value that can be obtained by including items up to a certain weight and capacity. We start by initializing the array with 0 values, and then we iterate through the items and their weights, and update the array based on whether it's more beneficial to include the item or not. This algorithm has a time complexity of O(nW), where n is the number of items and W is the capacity of the knapsack.

Another optimized solution is the greedy algorithm, which works by selecting the items with the highest value-to-weight ratio first and adding them to the knapsack until it reaches its capacity. While the greedy algorithm can provide a fast solution, it's not always optimal and can sometimes result in suboptimal solutions.

## Task 3

There are different implementations of the stair case problem in the following link:
https://www.enjoyalgorithms.com/blog/climbing-stairs-problem

Compare the time and space complexity of the different approaches

The time and space complexity of the different approaches to the staircase problem are as follows:

    Brute force approach (Recursion without memoization)
        Time complexity: O(2^n)
        Space complexity: O(n)

    Recursion with memoization
        Time complexity: O(n)
        Space complexity: O(n)

    Iterative approach (Dynamic Programming)
        Time complexity: O(n)
        Space complexity: O(n)

    Optimized iterative approach
        Time complexity: O(n)
        Space complexity: O(1)

As we can see, the brute force approach has the worst time complexity, taking exponential time to solve the problem. The other three approaches have linear time complexity and are much faster. The iterative approach and optimized iterative approach have the same time complexity, but the optimized approach uses constant space, which is more efficient than the other two approaches that use linear space.

In terms of space complexity, the brute force approach and recursion with memoization both use O(n) space, while the iterative approach and optimized iterative approach both use O(1) space.

## Task 4: Individual (at home)

- Difference between divide and conquer and dynamic programming
- State some application of dynamic programming
- Difference between recursion vs dynamic programming
- Difference between Top down and bottom up approaches to dynamic programming
- How to solve a Dynamic Programming Problem?

> Refer to the [links](#links) section below

## Links

- https://cpp.sh/
- [Recursion vs dynamic programming](https://www.geeksforgeeks.org/introduction-to-dynamic-programming-data-structures-and-algorithm-tutorials/)
- [How to solve a Dynamic Programming Problem ?](https://www.geeksforgeeks.org/solve-dynamic-programming-problem/)
