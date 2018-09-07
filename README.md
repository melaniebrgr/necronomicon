# CS

## Purpose

## Contents

1. Algorithms
    1. [Runtime Complexity Analysis](#runtime-complexity-analysis)
        1. [Asymptotic Analysis](#asymptotic-analysis)
        2. [Big-O Notation](#big-o-notation)
        3. [Orders of Common Functions](#orders-of-common-functions)
    2. Bitwise Operations
2. Data Structures


## Algorithms

### Runtime Complexity Analysis

Time Complexity describes the amount of time it takes to run an algorithm; Commonly estimated by counting the number of fixed time, runtime complexity considers the number of elementary operations performed by an algorithm.

Running times may vary between inputs, so a worst-case time complexity approach is assumed. This is the maximum amount of time required for inputs of a given size.

This complexity is expressed as a function of the size of the input, and is hard to estimate exactly, so we focus on the asymptotic behaviour of the complexity.

#### Asymptotic Analysis

Asymptotic Analysis is a method of describing limiting behaviour.

When something is Asymptotic it is said to be approaching a value or curve arbitrarily closesly as some sort of limit is taken.

A line or curve "A" that is Asymptotic to given curve "C" is called the Asymptote of "C".

<img src="./images/Asymptote.jpg" width="500" />


#### Big-O Notation

Big-O Notation describes the limiting behaviour of a function when the argument tends toward a particular value or infinity.

Big-O characterizes functions according to their growth rates. Different functions with the same growth rate may be represented using the same notation.

... More about Big O here

It is often helpful to think about the runtime complexity of a function to determine if there's a better (more efficient) solution to the problem you're trying to solve.

... Examples of simple functions and their Complexity here

<img src="./images/Common-Functions.png" width="500" />


#### Orders of Common Functions

Notation |  Name | Example
----------|------------|---------
**_O_(1)** | Constant | Determining if a binary number is even or odd.
**_O_(log log _n_)** | Double Logarithmic | Number of comparisons spent finding an item using interpolation search.å
**_O_(log _n_)** | Logarithmic | Finding an item in a sorted array with binary search.
**_O_((log _n_)<sup>c</sup>)** | Polylogarithmic | Solving matrix chain ordering.
**_O_(_n_<sup>c</sup>)** | Fractional Power | Searching in a k-d tree.
**_O_(_n_)** | Linear | Finding an item in an unsorted list. Adding two n-bit integers by ripple carry
**_O_(_n_ log<sup>*</sup> _n_)** | n log-star n | Performing triangulation of a simple polygon using Seidel's algorithm.
**_O_(_n_ log _n_)** or **_O_(log _n_!)** | Linearithmic, Loglinear, or Quasilinear | Performing a fast Fourier Transform. Fastest possible comparison sort. Heapsort and merge sort.
**_O_(_n_<sup>2</sup>)** | Quadratic | Multiplying two _n_-digit numbers by a simple algorithm. Bubble Sort, Selection Sort, Insertion Sort. Worst-case Quicksort, Shellsort, or Tree Sort.
**_O_(_n_<sup>c</sup>)** | Polynomial or Algebraic | Tree-adjoining grammar parsing. Maximum matching for bipartite graphs.
**_O_(c<sup>_n_</sup>)** | Exponential | Finding the exact solution to the Travelling Salesman problem using dynamic programming. Determining if two logical statements are equivalent using Brute-Force Search
**_O_(_n_!)** | Factorial | Solving the Travelling Salesman problem using brute-force search. Generating all unrestricted permutations of a poset.
