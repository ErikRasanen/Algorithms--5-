# Activities

## Task 1

Refer to the following link. Discuss how the Recursive Fibonacci with Memoization works:
https://www.cs.usfca.edu/~galles/visualization/DPFib.html

Recursive Fibonacci with memoization is a technique that optimizes the standard recursive Fibonacci algorithm by avoiding redundant calculations. In standard recursive Fibonacci, the same subproblem is calculated multiple times, leading to an exponential time complexity. With memoization, we store the results of each subproblem in a lookup table (a "memo"), so that we can reuse them later without recalculating them.

## Task 2

The stair case problem can be solved based on the Fibonacci series. There is a simple implementations in `./src/staircase2.cpp`.

- Explain how the code works. The following link might be useful:
  https://dev.to/alisabaj/the-climbing-staircase-problem-how-to-solve-it-and-why-the-fibonacci-numbers-are-relevant-3c4o

This program calculates the number of ways to reach the top of a staircase with s steps using a recursive implementation of the Fibonacci sequence.

The fib(n) function calculates the nth number in the Fibonacci sequence using recursion. It returns the value of n if n is less than or equal to 1, otherwise it recursively calculates the sum of the previous two numbers in the sequence using the fib(n - 1) and fib(n - 2) calls.

The countWays(s) function uses the fib function to calculate the (s+1)th Fibonacci number, which represents the number of ways to reach the top of a staircase with s steps. This is because each step can be reached by either taking one step from the previous stair or two steps from the stair before that, which corresponds to the Fibonacci sequence.

Finally, the main function sets the number of stairs s to 4 and calls the countWays function to print the number of ways to reach the top of the staircase with 4 steps.

Note that this implementation of the Fibonacci sequence using recursion is not very efficient, since it involves a lot of redundant calculations. For larger values of s, it would be better to use an iterative or memoization-based implementation.


- Modify the code to use Dynamic Programming (Memoization)

            #include <iostream>
            #include <unordered_map>
            using namespace std;

            unordered_map<int, int> memo;

            // A dynamic programming approach to find Nth fibonacci number
            int fib(int n)
            {
                if (memo.count(n) > 0) {
                    return memo[n];
                }
                if (n <= 1) {
                    memo[n] = n;
                    return n;
                }
                int result = fib(n - 1) + fib(n - 2);
                memo[n] = result;
                return result;
            }

            // Returns number of ways to reach s'th stair
            int countWays(int s)
            {
                return fib(s + 1);
            }

            // Driver C
            int main()
            {
                int s = 4;

                cout << "Number of ways = " << countWays(s);

                return 0;
            }

In this modified implementation, we use an unordered_map to store the previously calculated Fibonacci numbers. The fib(n) function first checks if the value of n is already present in the memoization table using memo.count(n). If it is, we simply return the value from the memoization table. If it's not present, we calculate the Fibonacci number using the recursive formula fib(n - 1) + fib(n - 2) and store it in the memoization table for future use.

This approach ensures that we only calculate each Fibonacci number once and use the previously calculated value for subsequent calculations, resulting in faster performance. The countWays function is unchanged and still returns the (s+1)th Fibonacci number, which represents the number of ways to reach the top of a staircase with s steps.

Finally, the main function sets the number of stairs s to 4 and calls the countWays function to print the number of ways to reach the top of the staircase with 4 steps.




## Task 3

Explain how the code in `./src/staircase3.cpp` works.

This code implements the Fibonacci sequence using dynamic programming and memoization to improve performance. The function fib takes two arguments: the index n of the Fibonacci number to calculate and an integer array dp that stores previously calculated Fibonacci numbers.

The function first checks if the Fibonacci number at index n is already calculated and stored in the dp array. If it is, we simply return the value from the dp array. If it's not present, we calculate the Fibonacci number using the recursive formula fib(n - 1, dp) + fib(n - 2, dp) and store it in the dp array for future use.

The countWays function initializes an integer array dp of size n+1 and sets all elements to -1 using memset. This is because we want to store Fibonacci numbers starting from index 0 up to index n in the dp array. We then call the fib function with n and the dp array as arguments to calculate the nth Fibonacci number and store it in the dp array.

Finally, the main function sets the value of n to 4 and calls the countWays function to print the nth Fibonacci number. This approach ensures that we only calculate each Fibonacci number once and use the previously calculated value for subsequent calculations, resulting in faster performance.


## Task 4: Individual (at home)

- There are `n` stairs, a person standing at the bottom wants to reach the top. Write a program that counts the number of ways someone can climb up to m stairs for a given value m. For example, if m is 4, it is possible to climb 1 stair or 2 stairs or 3 stairs or 4 stairs at a time. Make sure you use. Refer to the link below:
  https://www.geeksforgeeks.org/count-ways-reach-nth-stair/

        #include <iostream>
        using namespace std;

        int countWays(int n, int m)
        {
            if (n <= 1)
                return n;

            int ways[n+1];
            ways[0] = ways[1] = 1;

            for (int i = 2; i <= n; i++)
            {
                ways[i] = 0;
                for (int j = 1; j <= m && j <= i; j++)
                    ways[i] += ways[i-j];
            }

            return ways[n];
        }

        int main()
        {
            int n, m;
            cout << "Enter the number of stairs (n): ";
            cin >> n;
            cout << "Enter the maximum number of stairs that can be climbed at a time (m): ";
            cin >> m;
            cout << "Number of ways to climb " << n << " stairs with a maximum climb of " << m << " stairs at a time: " << countWays(n, m) << endl;
            return 0;
        }

The function countWays takes two arguments: n and m. n represents the total number of stairs, and m represents the maximum number of stairs that can be climbed at a time.

The function first checks if n is less than or equal to 1. If it is, we simply return n as there is only one way to climb one or zero stairs.

Otherwise, we create an integer array ways of size n+1 to store the number of ways to reach each stair. We initialize the values of ways[0] and ways[1] to 1 because there is only one way to reach the first and second stair.

We then use a nested loop to fill in the ways array starting from index 2 up to n. For each index i, we set the value of ways[i] to 0 and then loop through all the possible number of stairs that can be climbed at a time, from 1 up to m and up to the current index i. We then add the number of ways to reach the previous stair ways[i-j] to ways[i].

Finally, we return the value of ways[n], which represents the total number of ways to reach the nth stair.

In the main function, we prompt the user to enter the values of n and m, and then call the countWays function with these values as arguments. The program then prints out the number of ways to climb the stairs.


## Links

- https://cpp.sh/
- [leetcode.com](https://leetcode.com/problems/climbing-stairs/)
