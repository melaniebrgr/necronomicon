# N E C R O N O M I C O N

## Contents

1. [Data](#data)
    1. [Bit](#bit)
    2. [Nibble](#nibble)
    3. [Byte](#byte)
    4. [Word](#word)
2. [Data Structures](#data-structures)
3. [Algorithms](#algorithms)
    1. [Runtime Complexity Analysis](#runtime-complexity-analysis)
        1. [Asymptotic Analysis](#asymptotic-analysis)
        2. [Big-O Notation](#big-o-notation)
            1. [Dropping Non-Dominant Terms](#dropping-non-dominant-terms)
            2. [Recursive Runtimes](#recursive-runtimes)
            3. [Examples](#examples)
            4. [Orders of Common Functions](#orders-of-common-functions)
            5. [A Note About Space Complexity](#a-note-about-space-complexity)
    2. Bitwise Operations
    3. Lists, Arrays, Stacks
    4. Trees
    5. Sorting and Searching
    6. Pattern Matching and Parsing
    7. Hashing
    8. Sets and Disjoint Sets
    9. Graphs
    10. Dynamic Programming
    11. Search Space


## Data

### Nibble

### Bit

### Byte


### Word


## Data Structures

## Algorithms

### Runtime Complexity Analysis

Time Complexity describes the amount of time it takes to run an algorithm; Commonly estimated by counting the number of fixed time, runtime complexity considers the number of elementary operations performed by an algorithm.

Running times may vary between inputs, so a worst-case time complexity approach is assumed. This is the maximum amount of time required for inputs of a given size.

This complexity is expressed as a function of the size of the input, and is hard to estimate exactly, so we focus on the asymptotic behaviour of the complexity.

#### Asymptotic Analysis

Asymptotic Analysis is a method of describing limiting behaviour.

When something is Asymptotic it is said to be approaching a value or curve arbitrarily closesly as some sort of limit is taken.

A line or curve "A" that is Asymptotic to given curve "C" is called the Asymptote of "C".

<p align="center">
    <img src="./images/Asymptote.jpg" width="500" />
</p>


#### Big-O Notation

Big-O Notation describes the limiting behaviour of a function when the argument tends toward a particular value or infinity.

Big-O characterizes functions according to their growth rates. Different functions with the same growth rate may be represented using the same notation. It is often helpful to think about the runtime complexity of a function to determine if there's a better (more efficient) solution to the problem you're trying to solve.

"O" is used because growth rate is also referred to as the order of the function.

A description of a function in terms of Big-O usually only provides an upper bound on its growth rate. We rarely discuss the best case of a function, because it's not very useful: We can basically take any algorithm, special-case some input, and arrive at **_O_(1)**. Most of the time, worst-case and expected are the same, but they can sometimes differ. These are the two more important concepts. Big-O doesn't describe a particular case, just the asymptotic bounds, and can be used to describe particular cases. It is possible for **_O_(_n_)** code to run faster than **_O_(1)** for specific inputs. **Big-O just describes the rate of increase.**

Constants should be dropped. An algorithm that might be described as **_O_(2_n_)** is actually just **_O_(n)**. Again, specifics are often not important: Big-O simply allows us to express how a runtime scales.

##### Dropping Non-Dominant Terms

||||
-----|-----|-----|
**_O_(_n_<sup>2</sup> + _n_)**| = |**_O_(_n_<sup>2</sup>)**
|**_O_(_n_ + log _n_)**| = |**_O_(_n_)**
**_O_(5 * 2<sup>_n_</sup> + (1000 * _n_<sup>100</sup>))**| = |**_O_(2<sup>_n_</sup>)**

##### Recursive Runtimes

```
int f(int n) {
    if (n <= 1) {
        return 1;
    }

    return f(n - 1) + f(n - 1);
}
```

Each node has two children. Each tree will have depth _n_.  Each level has twice as many calls as the one above it.

|Level|Nodes|Also...|Or
|-|-|-|-|
|0|1| |2<sup>0</sup>
|1|2|2 * prev = 2|2<sup>1</sup>
|2|4|2 * prev = 2 * 2<sup>1</sup> = 2<sup>2</sup>|2<sup>2</sup>
|3|8|2 * prev = 2 * 2<sup>2</sup> = 2<sup>3</sup>|2<sup>3</sup>
|4|16|2 * prev = 2 * 2<sup>3</sup> = 2<sup>4</sup>|2<sup>4</sup>

2<sup>0</sup> +  2<sup>1</sup> + 2<sup>2</sup> + 2<sup>3</sup> + 2<sup>4</sup> + ... + 2<sup>_n_</sup> = 2<sup>n + 1</sup> - 1

This will often, but not always, look like **_O_(Branches<sup>depth</sup>)**, where branches is the number of times each recursive call branches. In this case this simplifies to **_O_(2<sup>_n_</sup>)**.

##### Examples

**Quicksort**

*Definition*: Pick a random pivot, then swap elements until the left of the pivot is less than the value of the pivot, and the right of the pivot is greater than the pivot. Then we recursively sort the left and right sides using the same process.

*Best Case*: If all elements are equal, quicksort will traverse the array once. This is **_O_(_n_)**.

*Worst Case*: If we get unlucky and the pivot is repeatedly the biggest element, in the case recursion doesn't divide the array in half and recurse over each half, it just shrinks the array by one. Degenerates to **_O_(_n_<sup>2</sup>)**.

*Expected Case*: We can expect a runtime of **_O_(N log N)**

----

<p align="center">
    <img src="./images/Common-Functions.png" width="500" />
</p>


##### Orders of Common Functions

Notation |  Name | Example
----------|------------|---------
**_O_(1)** | Constant | Determining if a binary number is even or odd.
**_O_(log log _n_)** | Double Logarithmic | Number of comparisons spent finding an item using interpolation search.
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

##### A Note About Space Complexity

Space Complexity is sometimes as important as runtime complexity, and should also be considered. Similar rules can apply, or at least the best/worst/expected cases can be considered in Big-O terms.

If we need to create an array of size _n_, this willl require **_O_(_n_)**. If we need a 2D Array of size _n_ * _n_, this will require **_O_(_n_<sup>2</sup>)** space.
