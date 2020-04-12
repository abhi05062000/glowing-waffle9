                    DAA LEARNING WEBSITE:-

                                                                      By- A SAMPATH ABHISHEK
                                                                      Reg no:-RA1811029010035
                    Welcome:-

 This tutorials will guide you to the most essential and basic concepts of   algorithms and design. 

        

CONTENTS OF THE COURSE:-

BRUTE FORCE
DIVIDE AND CONQUER
GREETY ALGORITHM
DYNAMIC PROGRAMMING
BACKTRACKING
BRANCH AND BOUND
Before moving on to the tutorials let us understand the very basics of time complexities and their analysis.

Time and Space Complexity:
Sometimes, there are more than one way to solve a problem. We need to learn how to compare the performance different algorithms and choose the best one to solve a particular problem. While analyzing an algorithm, we mostly consider time complexity and space complexity. Time complexity of an algorithm quantifies the amount of time taken by an algorithm to run as a function of the length of the input. Similarly, Space complexity of an algorithm quantifies the amount of space or memory taken by an algorithm to run as a function of the length of the input.

Time and space complexity depends on lots of things like hardware, operating system, processors, etc. However, we don't consider any of these factors while analyzing the algorithm. We will only consider the execution time of an algorithm.

Lets start with a simple example. Suppose you are given an array A and an integer x and you have to find if x exists in array A.

Simple solution to this problem is traverse the whole array A and check if the any element is equal to x.

for i : 1 to length of A
    if A[i] is equal to x
        return TRUE
return FALSE
Each of the operation in computer take approximately constant time. Let each operation takes c time. The number of lines of code executed is actually depends on the value of x. During analyses of algorithm, mostly we will consider worst case scenario, i.e., when x is not present in the array A. In the worst case, the if condition will run N times where N is the length of the array A. So in the worst case, total execution time will be (N∗c+c). N∗c for the if condition and c for the return statement ( ignoring some operations like assignment of i ).

As we can see that the total time depends on the length of the array A. If the length of the array will increase the time of execution will also increase.

Order of growth is how the time of execution depends on the length of the input. In the above example, we can clearly see that the time of execution is linearly depends on the length of the array. Order of growth will help us to compute the running time with ease. We will ignore the lower order terms, since the lower order terms are relatively insignificant for large input. We use different notation to describe limiting behavior of a function.

O-notation:
To denote asymptotic upper bound, we use O-notation. For a given function g(n), we denote by O(g(n)) (pronounced “big-oh of g of n”) the set of functions:
O(g(n))= { f(n) : there exist positive constants c and n0 such that 0≤f(n)≤c∗g(n) for all n≥n0 }

Ω-notation:
To denote asymptotic lower bound, we use Ω-notation. For a given function g(n), we denote by Ω(g(n)) (pronounced “big-omega of g of n”) the set of functions:
Ω(g(n))= { f(n) : there exist positive constants c and n0 such that 0≤c∗g(n)≤f(n) for all n≥n0 }

Θ-notation:
To denote asymptotic tight bound, we use Θ-notation. For a given function g(n), we denote by Θ(g(n)) (pronounced “big-theta of g of n”) the set of functions:
Θ(g(n))= { f(n) : there exist positive constants c1,c2 and n0 such that 0≤c1∗g(n)≤f(n)≤c2∗g(n) for all n>n0 }

enter image description here

   
                                                                   
1.Brute Force Algorithms
Brute Force Algorithms refers to a programming style that does not include any shortcuts to improve performance, but instead relies on sheer computing power to try all possibilities until the solution to a problem is found.

A classic example is the traveling salesman problem (TSP). Suppose a salesman needs to visit 10 cities across the country. How does one determine the order in which cities should be visited such that the total distance traveled is minimized? The brute force solution is simply to calculate the total distance for every possible route and then select the shortest one. This is not particularly efficient because it is possible to eliminate many possible routes through clever algorithms.

Another example: 5 digit password, in the worst case scenario would take 105 tries to crack.

The time complexity of brute force is O(n*m) . So, if we were to search for a string of ‘n’ characters in a string of ‘m’ characters using brute force, it would take us n * m tries.

 

2.Divide And Conquer
This technique can be divided into the following three parts:

Divide: This involves dividing the problem into some sub problem.
Conquer: Sub problem by calling recursively until sub problem solved.
Combine: The Sub problem Solved so that we will get find problem solution.
The following are some standard algorithms that follows Divide and Conquer  algorithm

Binary Search is a searching algorithm. In each step, the algorithm compares the input element x with the value of the middle element in array. If the values match, return the index of the middle. Otherwise, if x is less than the middle element, then the algorithm recurs for left side of middle element, else recurs for the right side of the middle element.
Quicksort is a sorting algorithm. The algorithm picks a pivot element, rearranges the array elements in such a way that all elements smaller than the picked pivot element move to left side of pivot, and all greater elements move to right side. Finally, the algorithm recursively sorts the subarrays on left and right of pivot element.
Merge Sort is also a sorting algorithm. The algorithm divides the array in two halves, recursively sorts them and finally merges the two sorted halves.
Closest Pair of Points The problem is to find the closest pair of points in a set of points in x-y plane. The problem can be solved in O(n^2) time by calculating distances of every pair of points and comparing the distances to find the minimum. The Divide and Conquer algorithm solves the problem in O(nLogn) time.
Strassen’s Algorithm is an efficient algorithm to multiply two matrices. A simple method to multiply two matrices need 3 nested loops and is O(n^3). Strassen’s algorithm multiplies two matrices in O(n^2.8974) time.
Cooley–Tukey Fast Fourier Transform (FFT) algorithm is the most common algorithm for FFT. It is a divide and conquer algorithm which works in O(nlogn) time.
Karatsuba algorithm for fast multiplication it does multiplication of two n-digit numbers in at most 3 n^{\log_23}\approx 3 n^{1.585}single-digit multiplications in general (and exactly n^{\log_23} when n is a power of 2). It is therefore faster than the classical algorithm, which requires n2 single-digit products. If n = 210 = 1024, in particular, the exact counts are 310 = 59, 049 and (210)2 = 1, 048, 576, respectively.
Divide And Conquer algorithm :

DAC(a, i, j)
{
    if(small(a, i, j))
      return(Solution(a, i, j))
    else 
      m = divide(a, i, j)               // f1(n)
      b = DAC(a, i, mid)                 // T(n/2)
      c = DAC(a, mid+1, j)            // T(n/2)
      d = combine(b, c)                 // f2(n)
   return(d)
}
Recurrence Relation for DAC algorithm :
This is recurrence relation for above program.

           O(1) if n is small
T(n) =     f1(n) + 2T(n/2) + f2(n)
Example:
To find the maximum and minimum element in a given array.

Input: { 70, 250, 50, 80, 140, 12, 14 }
Output: The minimum number in a given array is : 12
The maximum number in a given array is : 250
Dynamic Programming
 
 
Dynamic Programming is mainly an optimization over plain recursion. Wherever we see a recursive solution that has repeated calls for same inputs, we can optimize it using Dynamic Programming. The idea is to simply store the results of subproblems, so that we do not have to re-compute them when needed later. This simple optimization reduces time complexities from exponential to polynomial. 

Basic Problems :

Ugly numbers
Fibonacci numbers
nth Catalan Number
Bell Numbers (Number of ways to Partition a Set)
Binomial Coefficient
Permutation Coefficient
Tiling Problem
Gold Mine Problem
Coin change problem
Friends Pairing Problem
Subset Sum Problem
Subset Sum Problem in O(sum) space
Subset with sum divisible by m
Largest divisible pairs subset
Perfect Sum Problem (Print all subsets with given sum)
Compute nCr % p
Choice of area
Cutting a Rod
Tiling with Dominoes
Painting Fence Algorithm
Newman–Shanks–Williams prime
Assembly line scheduling
Golomb sequence
Moser-de Bruijn Sequence
Newman-Conway Sequence
Find maximum length Snake sequence
Print n terms of Newman-Conway Sequence
Print Fibonacci sequence using 2 variables
Print Fibonacci Series in reverse order
Count even length binary sequences with same sum of first and second half bits
Sequences of given length where every element is more than or equal to twice of previous
Longest Common Subsequence
Longest Repeated Subsequence
Longest Increasing Subsequence
A Space Optimized Solution of LCS
LCS (Longest Common Subsequence) of three strings
Maximum sum Bi-tonic Sub-sequence
Maximum Sum Increasing Subsequence
Maximum product of an increasing subsequence
Count all subsequences having product less than K
Maximum subsequence sum such that no three are consecutive
Longest subsequence such that difference between adjacents is one
Maximum length subsequence with difference between adjacent elements as either 0 or 1
Maximum sum increasing subsequence from a prefix and a given element after prefix is must
Backtracking 
 
Backtracking is an algorithmic-technique for solving problems recursively by trying to build a solution incrementally, one piece at a time, removing those solutions that fail to satisfy the constraints of the problem at any point of time (by time, here, is referred to the time elapsed till reaching any level of the search tree).

For example, consider the SudoKo solving Problem, we try filling digits one by one. Whenever we find that current digit cannot lead to a solution, we remove it (backtrack) and try next digit. This is better than naive approach (generating all possible combinations of digits and then trying every combination one by one) as it drops a set of permutations whenever it backtracks.



if we write simple recursive solution for Fibonacci Numbers, we get exponential time complexity and if we optimize it by storing solutions of subproblems, time complexity reduces to linear.

 

Greedy Algorithms
 
Greedy is an algorithmic paradigm that builds up a solution piece by piece, always choosing the next piece that offers the most obvious and immediate benefit. So the problems where choosing locally optimal also leads to global solution are best fit for Greedy.

For example consider the Fractional Knapsack Problem. The local optimal strategy is to choose the item that has maximum value vs weight ratio. This strategy also leads to global optimal solution because we allowed to take fractions of an item.

Standard Greedy Algorithms :

Activity Selection Problem
Egyptian Fraction
Job Sequencing Problem
Job Sequencing Problem (Using Disjoint Set)
Job Sequencing Problem – Loss Minimization
Job Selection Problem – Loss Minimization Strategy | Set 2
Huffman Coding
Efficient Huffman Coding for sorted input
Huffman Decoding
Water Connection Problem
Policemen catch thieves
Minimum Swaps for Bracket Balancing
Fitting Shelves Problem
Assign Mice to Holes
Branch and Bound Algorithm
Branch and bound is an algorithm design paradigm which is generally used for solving combinatorial optimization problems. These problems are typically exponential in terms of time complexity and may require exploring all possible permutations in worst case. The Branch and Bound Algorithm technique solves these problems relatively quickly.

Let’s see the Branch and Bound Approach to solve the 0/1 Knapsack problem: The Backtracking Solution can be optimized if we know a bound on best possible solution subtree rooted with every node. If the best in subtree is worse than current best, we can simply ignore this node and its subtrees. So we compute bound (best solution) for every node and compare the bound with current best solution before exploring the node.

Example bounds used in below diagram are, A down can give $315, B down can $275, C down can $225, D down can $125 and E down can $30.



 

 

 
