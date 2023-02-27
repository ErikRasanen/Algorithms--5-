# Activities

## Task 1

- Refer to the following link. Discuss how the
  Recursive Factorial works:
  https://www.cs.usfca.edu/~galles/visualization/RecFact.html

Recursive factorial is a function that calculates the factorial of a given number using a recursive approach. The factorial of a positive integer n is defined as the product of all positive integers up to and including n. For example, the factorial of 5 (written as 5!) is calculated as follows:

5! = 5 x 4 x 3 x 2 x 1 = 120

Here's how the recursive factorial works:

    The function takes a positive integer n as input.

    If n is equal to 1, the function returns 1 (base case).

    If n is greater than 1, the function calls itself recursively with n-1 as the argument and multiplies the result by n.

    The recursion continues until the base case is reached, at which point the function returns the final result.

- Refer to the following link. Discuss how the Recursive Fibonacci works:
  https://www.cs.usfca.edu/~galles/visualization/DPFib.html

  Recursive Fibonacci is a function that calculates the nth Fibonacci number using a recursive approach. The Fibonacci sequence is a series of numbers in which each number is the sum of the two preceding numbers. The first two numbers in the sequence are 0 and 1. For example, the first ten Fibonacci numbers are:

0, 1, 1, 2, 3, 5, 8, 13, 21, 34

Here's how the recursive Fibonacci works:

    The function takes a positive integer n as input.

    If n is equal to 0 or 1, the function returns n (base cases).

    If n is greater than 1, the function calls itself recursively with n-1 and n-2 as the arguments and adds the results.

    The recursion continues until the base case is reached, at which point the function returns the final result.

## Task 2

There are `n` stairs, a person standing at the bottom wants to reach the top. The person can climb either 1 stair or 2 stairs at a time. There is a simple implementations in `./src/` folder. Discuss how the code works.

Code counts the steps taken and also considers if 1 or 2 steps taken at a time.

## Task 3

- There are `n` stairs, a person standing at the bottom wants to reach the top. The person can climb either 1 stair or 2 stairs or **3 stairs** at a time. Write a program that counts the number of ways, the person can reach the top. You can use the following program as a starter `./src/staircase1.cpp`. Also the link below might useful:
  https://www.includehelp.com/cpp-programs/stair-case-program-to-solve-the-staircase-problem.aspx

  #include <iostream>
using namespace std;

int number_of_paths(int n)
{
    if (n <= 0)
        return 0;
    if (n == 1)
        return 1;
    if (n == 2)
        return 2;
    if (n == 3)
        return 4;

    return number_of_paths(n - 1) + number_of_paths(n - 2) + number_of_paths(n - 3);
}

int main()
{

    cout << "number of paths =  " << number_of_paths(4);
    return 0;
}

## Task 4: Individual (at home)

- What are the pros/cons of recursive over iterative Programming?

Both recursive and iterative programming have their own advantages and disadvantages depending on the problem at hand. Here are some pros and cons of recursive and iterative programming:

Recursive Programming:

Pros:

    Recursive programming is often more intuitive and easier to understand for certain types of problems, especially those that have a recursive definition, such as traversing a tree data structure.
    Recursive programming can make code more concise and elegant by reducing the amount of repetitive code.
    Recursive programming can be useful for problems that have multiple recursive subproblems.

Cons:

    Recursive programming can be less efficient in terms of memory and time complexity because it requires additional memory for each recursive call on the stack.
    Recursive programming can cause issues with stack overflow if the recursion is too deep, which can crash the program.

Iterative Programming:

Pros:

    Iterative programming is often more efficient in terms of memory and time complexity because it does not require additional memory for each iteration.
    Iterative programming can be more flexible and easier to optimize for different hardware architectures.
    Iterative programming can be easier to debug since the program can be paused and resumed at any point.

Cons:

    Iterative programming can be more difficult to understand for certain types of problems, especially those that have a recursive definition.
    Iterative programming can be more verbose and harder to write for certain problems that have many nested loops.
    Iterative programming can be harder to implement for certain data structures, such as trees and graphs, that are more naturally suited to recursive algorithms.

In general, recursive programming is often used when the problem has a recursive definition, and when readability and elegance are a priority. Iterative programming is often used when efficiency and performance are a priority, and when the problem can be more easily expressed using loops and iterations.

- Difference between recursion and induction.

Recursion is a technique in computer science that involves solving a problem by breaking it down into smaller, simpler subproblems that are similar to the original problem. A recursive algorithm is one that calls itself with a smaller input until a base case is reached. Recursion is often used to solve problems that have a recursive structure, such as traversing a tree or a linked list.

Induction, on the other hand, is a technique in mathematics that involves proving a statement is true for all positive integers by showing that it holds for the base case (usually 1), and then showing that if it holds for a particular integer k, then it must also hold for k+1. Induction is often used to prove the correctness of recursive algorithms or to prove mathematical theorems.

The key difference between recursion and induction is in their methodology. Recursion involves breaking down a problem into smaller subproblems and solving them recursively, while induction involves proving a statement is true for all positive integers by using a base case and an inductive step. In computer science, recursion and induction are often used together to prove the correctness of recursive algorithms. In mathematics, induction is a more general technique that can be used to prove a wide variety of statements, not just those related to recursion.


> Refer to the [links](#links) section below.

## Links

- https://cpp.sh/
- [Difference Between Recursion and Induction](https://www.geeksforgeeks.org/difference-between-recursion-and-induction/)
- [Recursion vs Iterative Programming](https://www.softwaretestinghelp.com/recursion-in-cpp/)
