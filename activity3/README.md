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

        Both Divide and Conquer (D&C) and Dynamic Programming (DP) are problem-solving techniques used in algorithm design, but they differ in their approach to solving problems.

        Divide and Conquer is a problem-solving strategy that involves breaking down a problem into smaller sub-problems until they become simple enough to solve directly. This process is done recursively until the sub-problems are small enough to be solved easily. Once the sub-problems are solved, the solutions are combined to solve the original problem. D&C works well for problems that can be divided into sub-problems that are independent of each other, and where the solutions to the sub-problems can be combined to solve the original problem.

        On the other hand, Dynamic Programming is an algorithmic technique that solves problems by breaking them down into smaller sub-problems and solving each sub-problem once, storing its solution in memory. This approach reduces the number of redundant calculations and improves the time complexity of the algorithm. DP works well for problems where the optimal solution can be found by solving a sequence of sub-problems, and where the optimal solution to the original problem can be constructed from the solutions to the sub-problems.

        To summarize, both D&C and DP solve problems by dividing them into smaller sub-problems, but D&C solves sub-problems recursively and independently, while DP solves sub-problems iteratively and stores the solutions in memory for future use.

- State some application of dynamic programming

Dynamic programming has many applications across various fields, some of which are:

        Optimization problems: Dynamic programming can be used to solve optimization problems, such as finding the shortest path in a graph, maximizing profits in a business, or minimizing the cost of production.

        Image processing: Dynamic programming algorithms are used in image processing to improve the quality of an image, such as enhancing the resolution, reducing noise, or smoothing edges.

        Artificial intelligence: Dynamic programming is used in artificial intelligence to solve problems such as game theory, planning, and optimization.

        Bioinformatics: Dynamic programming is used in bioinformatics to solve problems such as sequence alignment, protein folding, and gene prediction.

        Finance: Dynamic programming is used in finance to solve problems such as portfolio optimization, risk management, and option pricing.

        Natural language processing: Dynamic programming is used in natural language processing to solve problems such as speech recognition, machine translation, and text summarization.

        Robotics: Dynamic programming is used in robotics to solve problems such as motion planning, pathfinding, and control.


- Difference between recursion vs dynamic programming

        Approach:

        Recursion is a top-down approach, where a problem is divided into smaller subproblems until the base case is reached. Each subproblem is then solved and the solutions are combined to solve the original problem.
        Dynamic programming is a bottom-up approach, where the problem is first broken down into simpler subproblems and then solved iteratively. The solutions of subproblems are stored in a table and used to solve the larger problem.

        Memory Usage:

        Recursion often involves creating multiple function calls and storing their intermediate results on the call stack. This can lead to excessive memory usage and potential stack overflow issues.
        Dynamic programming, on the other hand, stores intermediate results in a table, which can be accessed and reused multiple times. This can lead to more efficient use of memory.

        Performance:

        Recursion can have higher time complexity due to repeated function calls and redundant calculations.
        Dynamic programming, however, can be more efficient as it avoids redundant calculations and optimizes the use of memory.

        Application:

        Recursion is generally used for problems where the solution depends on the solution to smaller subproblems.
        Dynamic programming is commonly used for optimization problems, where the goal is to find the optimal solution among a set of subproblems.

- Difference between Top down and bottom up approaches to dynamic programming

        The main difference between the top-down and bottom-up approaches in dynamic programming is the order in which subproblems are solved.

        In the top-down approach, also known as the memoization approach, we start with the original problem and break it down into smaller subproblems. Then, we solve each subproblem only once and store its result in a lookup table or cache, so that we can access it later if the same subproblem occurs again. This approach is similar to recursion, as it solves the problem by recursively breaking it down into smaller subproblems. The top-down approach typically uses recursion or a recursive function with memoization.

        In the bottom-up approach, also known as the tabulation approach, we start with the subproblems and solve them in a specific order, typically from smallest to largest, until we solve the original problem. In this approach, we create a table or array to store the results of the subproblems and use the results of the previously solved subproblems to solve the current subproblem. This approach is usually implemented using loops instead of recursion and is more efficient in terms of space complexity.

        Overall, the main difference between the two approaches is the order in which the subproblems are solved. The top-down approach solves the subproblems recursively and stores their results in memory, while the bottom-up approach iteratively solves the subproblems and stores their results in a table.

- How to solve a Dynamic Programming Problem?

            Identify if the problem can be broken down into smaller subproblems.
            Determine the recurrence relation or the formula that relates the current subproblem to its smaller subproblems.
            Identify the base cases, which are the smallest subproblems that can be solved directly.
            Decide whether to use a top-down (memoization) or bottom-up (tabulation) approach to solve the problem.
            If using a top-down approach, create a memoization table to store the solutions to the subproblems that have already been solved.
            If using a bottom-up approach, create a tabulation table to store the solutions to the subproblems in a bottom-up manner.
            Populate the table by solving the subproblems in the order defined by the recurrence relation.
            Return the solution to the original problem, which can be found in the last entry of the table.

        It is important to note that not all dynamic programming problems require all these steps, and sometimes modifications or variations may be required based on the specific problem. However, these steps provide a general framework for solving dynamic programming problems.

> Refer to the [links](#links) section below

## Links

- https://cpp.sh/
- [Recursion vs dynamic programming](https://www.geeksforgeeks.org/introduction-to-dynamic-programming-data-structures-and-algorithm-tutorials/)
- [How to solve a Dynamic Programming Problem ?](https://www.geeksforgeeks.org/solve-dynamic-programming-problem/)
