

# Common Patterns

<details>
<summary> Mathematics
</summary>

## Mathematics

- https://www.youtube.com/watch?v=DROZVHObeko : Permutation formula | Probability and combinatorics | Probability and Statistics | Khan Academy
		- No of ways in which n objects can be placed in k spots : nPk = n!/(n-k)!
		- n is the no of objects, k is the no of slots.
- https://youtu.be/Mm0VNPars2M : permutation for repeating chars : nPk/[!(no of times a numer is repeating) *!(no of times next numer is repeating)...]

- https://www.youtube.com/watch?v=p8vIcmr_Pqo : Combination formula | Probability and combinatorics | Probability and Statistics | Khan Academy
		- In combination combinations with same elments is considered as single combination, eg : ABCD & DACB both are same in combination but diff in permutation
		- No of combinations in which n objects can be placed in k spots : ** nCk = n!/(k! * (n-k)!) **

		
- https://www.youtube.com/watch?v=HuZJqRDOPo0 : Find duplicates in O(n) time and O(1) extra space | GeeksforGeeks
		- find A[abs(A[i])], if +ve mark as -ve, if -ve number is duplicate
		

- https://www.geeksforgeeks.org/c-program-find-gcd-hcf-two-numbers/

- https://www.youtube.com/watch?v=dolcMgiJ7I0 : Finding all factors of a number

- https://www.youtube.com/watch?v=6PDtgHhpCHo : Prime factorization of a number

- https://www.interviewbit.com/tutorial/base-number-system/ : base number system

- https://www.interviewbit.com/tutorial/binary-number-system/

- https://practice.geeksforgeeks.org/tracks/ppc-mathematics/?batchId=221 : find the count of digits present in this number, Arithmetic Progression, Geometric Progression, quadratic equation, Mean, Median, prime number(Sieve of Eratosthenes), factorial, Permutation, Combination, 

- https://www.youtube.com/watch?v=qwh3VH5rnGA : HCF & LCM

- https://medium.com/solvingalgo/solving-algorithmic-problems-find-a-duplicate-in-an-array-3d9edad5ad41#:~:text=The%20solution%20is%20to%20consider,the%20value%20of%20that%20index.&text=We%20iterate%20over%20each%20element,its%20index%20is%20a%20duplicate. : Find duplicate number

- sum of numbers from 1 to n = n(n+1)/2

### Karatsuba Multiplication


</details>

<details>
<summary> Bit Manipulation
</summary>

## Bit Manipulation

- https://www.hackerearth.com/practice/basic-programming/bit-manipulation/basics-of-bit-manipulation/tutorial/

- https://www.geeksforgeeks.org/find-the-element-that-appears-once/

- https://www.youtube.com/watch?v=4u0fSw1AOR4&feature=youtu.be : Reverse Bits

- https://www.youtube.com/watch?v=mJG1DManmLc : How to Swap Two Numbers using XOR Operator in Java.
		- Swap a & b using xor : 
		``` a=a^b
			b=a^b
			a=a^b
		``` 
		
- https://www.geeksforgeeks.org/find-element-appears-array-every-element-appears-twice/?ref=rp : Find the element that appears once in an array where every other element appears twice
		- xor of a number with itself is 0
		- Do a xor of all the numbers in array and u will get the result
		
		
</details>

<details>
<summary> Complexity Analysis
</summary>

## Complexity Analysis

- https://adrianmejia.com/most-popular-algorithms-time-complexity-every-programmer-should-know-free-online-tutorial-course/
- https://www.youtube.com/watch?v=VHNJbXqq2Is : Big O Notation

- https://www.youtube.com/watch?v=v4cd1O4zkGw : Big O Notation, HackerRank

- https://www.youtube.com/watch?v=iOq5kSKqeR4 : Asymptotic Notation

- https://www.youtube.com/watch?v=MyeV2_tGqvw : What Is Big O? (Comparing Algorithms)

- https://www.youtube.com/watch?v=mIjuDg8ky4U : Big O Part 3 – Quadratic Complexity

- https://www.youtube.com/watch?v=Hatl0qrT0bI : Big O Part 4 – Logarithmic Complexity

- https://www.youtube.com/watch?v=i7CmolBf3HM : Big O Part 5 – Linearithmic Complexity

- https://medium.com/karuna-sehgal/a-simplified-explanation-of-the-big-o-notation-82523585e835

- https://www.freecodecamp.org/news/big-o-notation-simply-explained-with-illustrations-and-video-87d5a71c0174/

- https://www.geeksforgeeks.org/analysis-algorithms-big-o-analysis/

**Definition**
- It is about, how quickly runtime grows relative to the input, as the input gets arbitrarily large.
- Big O is used to identify runtime of algo growth for the worst case scenario
- Best case time complexity is represented by Omega Ω
- When best case and worst case is same we can represent it with theta  θ
- used to compare the efficiency of an algorithm
- to measure, how quickly the runtime of an algorithm grows when input size grows.
- while calculating the O(n) complexity we ignore the smaller terms and the constants


**Constant time Complexity**
- O(1)
- find the length of a collection


**Logarithmic Complexity**
- O(log n)
- Binary search

**Linear time complexity**
- O(n)
- Linear search

**Linearithmic Complexity**
- O(n*log n)
- Merge sort

**Quadratic Complexity**
- O(n^2)
- bubble sort

**Exponential**
- O(2^n)

**Factorial**
- O(n!) : Travelling Salesman



</details>





<details>
<summary> Sorting Algorithms
</summary>

## Sorting Algorithms

- https://www.hackerearth.com/practice/algorithms/sorting/bubble-sort/tutorial/ : all sorting algos

- https://www.youtube.com/watch?v=6Gv8vg0kcHc : Algorithms: Bubble Sort

- https://www.youtube.com/watch?v=f8hXR_Hvybo : Selection Sort

- https://www.youtube.com/watch?v=kU9M51eKSX8 : Insertion Sort

- https://www.youtube.com/watch?v=OKd534EWcdk : Learn Counting Sort Algorithm in LESS THAN 6 MINUTES!

- https://www.youtube.com/watch?v=sWtYJv_YXbo : Merge Sort

- https://www.youtube.com/watch?v=KF2j-9iSf4Q : Merge Sort : HackerRank

- https://www.youtube.com/watch?v=8hHWpuAPBHo : Quicksort Part 1 - Algorithm
- https://www.youtube.com/watch?v=39BV3_DONJc : Quicksort Part 2 - Implementation

- https://www.youtube.com/watch?v=-7pzsM6gxgY : QuickSort Algorithm - Divide and Conquer

- https://www.youtube.com/watch?v=Hoixgm4-P4M : Quick sort in 4 minutes

- https://www.youtube.com/watch?v=COk73cpQbFQ : Quicksort algorithm

- https://www.youtube.com/watch?v=EidLQSNUXV4 : Design and Analysis of Algorithms - Time Complexity Comparisons Between Various Sorting Algorithms



</details>


<details>
<summary> Two Pointer 
</summary>

## Two Pointer 

- https://www.interviewbit.com/tutorial/two-pointers/
- file:///C:/Users/hmnsh/Documents/study/library/AlgoDs/EDUCAT~1.IO-/EDUCAT~1.IO-/33C29~1.PAT/158EC~1.INT/INTROD~1.HTM : Educative Grokking the coding
- https://leetcode.com/problems/squares-of-a-sorted-array/ : Squares of a Sorted Array (easy)
- file:///C:/Users/hmnsh/Documents/study/library/AlgoDs/EDUCAT~1.IO-/EDUCAT~1.IO-/33C29~1.PAT/551C4~1.TRI/11TRIP~1.HTM : Triplet Sum to Zero
- file:///C:/Users/hmnsh/Documents/study/library/AlgoDs/EDUCAT~1.IO-/EDUCAT~1.IO-/3.%20Pattern%20Two%20Pointers/9.%20Dutch%20National%20Flag%20Problem%20(medium)/1.1%20Dutch%20National%20Flag%20Problem%20(medium)%20-.html : Sort Colors / Sort array with 3 types of numbers in place in 1 iteration : [2,0,2,1,1,0] -> [0,0,1,1,2,2]
- file:///C:/Users/hmnsh/Documents/study/library/AlgoDs/EDUCAT~1.IO-/EDUCAT~1.IO-/3.%20Pattern%20Two%20Pointers/13.%20Solution%20Review%20Problem%20Challenge%202/1.1%20Solution%20Review_%20Problem%20Challenge%202%20-.html : Comparing Strings containing Backspaces

- file:///C:/Users/hmnsh/Documents/study/library/AlgoDs/EDUCAT~1.IO-/EDUCAT~1.IO-/3.%20Pattern%20Two%20Pointers/15.%20Solution%20Review%20Problem%20Challenge%203/1.1%20Solution%20Review_%20Problem%20Challenge%203.html : Minimum Window Sort

- 

Two Pointers is a pattern where two pointers iterate through the data structure in tandem until one or both of the pointers hit a certain condition.
Two Pointers is often useful when searching pairs in a sorted array or linked list; for example, when you have to compare each element of 
an array to its other elements.


Two pointers are needed because with just 1 pointer, you would have to continually loop back through the array to find the answer. 
This back and forth with a single iterator is inefficient for time and space complexity — a concept referred to as asymptotic analysis. 
While the brute force or naive solution with 1 pointer would work, it will produce something along the lines of O(n²). 
In many cases, two pointers can help you find a solution with better space or runtime complexity.

**Ways to identify when to use the Two Pointer method:**
It will feature problems where you deal with sorted arrays (or Linked Lists) and need to find a set of elements that fulfill certain constraints
The set of elements in the array is a pair, a triplet, or even a subarray


**Here are some problems that feature the Two Pointer pattern:**
- Squaring a sorted array (easy)
- Triplets that sum to zero (medium)
- Comparing strings that contain backspaces (medium)

</details>

<details>
<summary> Fast and Slow pointers
</summary>

## Fast and Slow pointers

Eg : https://www.geeksforgeeks.org/function-to-check-if-a-singly-linked-list-is-palindrome/   approach 3
	
The Fast and Slow pointer approach, also known as the Hare & Tortoise algorithm, is a pointer algorithm that uses two pointers 
which move through the array (or sequence/linked list) at different speeds. This approach is quite useful when dealing with 
cyclic linked lists or arrays.
By moving at different speeds (say, in a cyclic linked list), the algorithm proves that the two pointers are bound to meet. 
The fast pointer should catch the slow pointer once both the pointers are in a cyclic loop.

**How do you identify when to use the Fast and Slow pattern?**
The problem will deal with a loop in a linked list or array
When you need to know the position of a certain element or the overall length of the linked list.

**When should I use it over the Two Pointer method mentioned above?**
There are some cases where you shouldn’t use the Two Pointer approach such as in a singly linked list where you can’t move in a backwards direction. 
An example of when to use the Fast and Slow pattern is when you’re trying to determine if a linked list is a palindrome.


**Problems featuring the fast and slow pointers pattern:**
- Linked List Cycle (easy)
- Palindrome Linked List (medium)
- Cycle in a Circular Array (hard)

</details>


<details>
<summary> Sliding Window
</summary>

## Sliding Window

Eg : https://www.geeksforgeeks.org/find-zeroes-to-be-flipped-so-that-number-of-consecutive-1s-is-maximized/

- file:///C:/Users/hmnsh/Documents/study/library/AlgoDs/EDUCAT~1.IO-/EDUCAT~1.IO-/2.%20Pattern%20Sliding%20Window/1.%20Introduction/1.1%20Introduction%20-%20Grokking%20the%20Coding%20Interview_%20Patterns%20for%20Coding%20Questions.html : Intro , Grokking the coding interview

- file:///C:/Users/hmnsh/Documents/study/library/AlgoDs/EDUCAT~1.IO-/EDUCAT~1.IO-/25393~1.PAT/2FBBA~1.MAX/11MAXI~1.HTM : Maximum Sum Subarray of Size K (easy)
- file:///C:/Users/hmnsh/Documents/study/library/AlgoDs/EDUCAT~1.IO-/EDUCAT~1.IO-/25393~1.PAT/4633A~1.LON/11LONG~1.HTM : Longest Substring with K Distinct Characters (medium)
- file:///C:/Users/hmnsh/Documents/study/library/AlgoDs/EDUCAT~1.IO-/EDUCAT~1.IO-/25393~1.PAT/6C072~1.NO-/11NO-R~1.HTM : No-repeat Substring (hard)
- https://leetcode.com/problems/max-consecutive-ones-iii/ : Max Consecutive Ones
	
The Sliding Window pattern is used to perform a required operation on a specific window size of a given array or linked list, 
such as finding the longest subarray containing all 1s. Sliding Windows start from the 1st element and keep shifting right by one 
element and adjust the length of the window according to the problem that you are solving. In some cases, the window size remains 
constant and in other cases the sizes grows or shrinks.

**Following are some ways you can identify that the given problem might require a sliding window:**
- The problem input is a linear data structure such as a linked list, array, or string
- You’re asked to find the longest/shortest substring, subarray, or a desired value


**Common problems you use the sliding window pattern with:**
- Maximum sum subarray of size ‘K’ (easy)
- Longest substring with ‘K’ distinct characters (medium)
- String anagrams (hard)
- Maximum Sum Subarray of Size K (easy) : https://www.educative.io/courses/grokking-the-coding-interview/JPKr0kqLGNP
- Smallest Subarray with a given sum (easy) : https://www.educative.io/courses/grokking-the-coding-interview/7XMlMEQPnnQ
- Longest Substring with K Distinct Characters (medium) : https://www.educative.io/courses/grokking-the-coding-interview/YQQwQMWLx80
- Fruits into Baskets (medium)
- No-repeat Substring (hard)
- Longest Substring with Same Letters after Replacement (hard)
- Longest Subarray with Ones after Replacement (hard)

**Sample Template**

- https://leetcode.com/problems/max-consecutive-ones-iii/

```
public int longestOnes(int[] A, int K) {
		int windowStart = 0;
		int maxLen = 0;
		int windowEnd = 0;
		int noOfZeros = 0;
		for (int i = 0; i < A.length; i++) {

			if (A[i] == 1) {
				windowEnd = i;
			} else {

				while (noOfZeros == K) {
					if (A[windowStart] == 0)
						noOfZeros--;
					windowStart++;
				}

				noOfZeros++;
				windowEnd = i;
			}
			maxLen = Math.max(maxLen, windowEnd - windowStart + 1);
		}
		return maxLen;
	}

```
	
</details>


<details>
<summary> Merge Intervals
</summary>
	
## Merge Intervals

- file:///C:/Users/hmnsh/Documents/study/library/AlgoDs/EDUCAT~1.IO-/EDUCAT~1.IO-/5.%20Pattern%20Merge%20Intervals/4.%20Intervals%20Intersection%20(medium)/1.1Intervals%20Intersection%20(medium)%20-%20Grokking%20the%20Coding%20Interview_%20Patterns%20for%20Coding%20Questions.html : Intervals Intersection

- file:///C:/Users/hmnsh/Documents/study/library/AlgoDs/EDUCAT~1.IO-/EDUCAT~1.IO-/5.%20Pattern%20Merge%20Intervals/7.%20Solution%20Review%20Problem%20Challenge%201/1.1Solution%20Review_%20Problem%20Challenge%201%20-.html : Minimum Meeting Rooms required

- file:///C:/Users/hmnsh/Documents/study/library/AlgoDs/EDUCAT~1.IO-/EDUCAT~1.IO-/5.%20Pattern%20Merge%20Intervals/9.%20Solution%20Review%20Problem%20Challenge%202/1.1Solution%20Review_%20Problem%20Challenge%202%20-.html : Maximum CPU Load (hard)

- file:///C:/Users/hmnsh/Documents/study/library/AlgoDs/EDUCAT~1.IO-/EDUCAT~1.IO-/5.%20Pattern%20Merge%20Intervals/11.%20Solution%20Review%20Problem%20Challenge%203/1.1.1Solution%20Review_%20Problem%20Challenge%203%20-.html : Employee Free Time (hard)

The Merge Intervals pattern is an efficient technique to deal with overlapping intervals. In a lot of problems involving intervals, 
you either need to find overlapping intervals or merge intervals if they overlap. The pattern works like this:
Given two intervals (‘a’ and ‘b’), there will be six different ways the two intervals can relate to each other:

Understanding and recognizing these six cases will help you help you solve a wide range of problems from inserting intervals to 
optimizing interval merges.
**How do you identify when to use the Merge Intervals pattern?**
If you’re asked to produce a list with only mutually exclusive intervals
If you hear the term “overlapping intervals”.



</details>

<details>
<summary> Cyclic sort
</summary>

## Cyclic sort

- file:///C:/Users/hmnsh/Documents/study/library/AlgoDs/EDUCAT~1.IO-/EDUCAT~1.IO-/6.%20Pattern%20Cyclic%20Sort/1.%20Introduction/Introduction%20-%20Grokking%20the%20Coding%20Interview_%20Patterns%20for%20Coding%20Questions.html : Introduction

- file:///C:/Users/hmnsh/Documents/study/library/AlgoDs/EDUCAT~1.IO-/EDUCAT~1.IO-/6.%20Pattern%20Cyclic%20Sort/2.%20Cyclic%20Sort%20(easy)/1.1%20Cyclic%20Sort%20(easy)%20-%20Grokking%20the%20Coding%20Interview_%20Patterns%20for%20Coding%20Questions.html : Cyclic Sort (easy)

- file:///C:/Users/hmnsh/Documents/study/library/AlgoDs/EDUCAT~1.IO-/EDUCAT~1.IO-/6.%20Pattern%20Cyclic%20Sort/4.%20Find%20all%20Missing%20Numbers%20(easy)/1.1Find%20all%20Missing%20Numbers%20(easy)%20-%20Grokking%20the%20Coding%20Interview_%20Patterns%20for%20Coding%20Questions.html : Find all Missing Numbers (easy)

- Find the Missing Number : https://leetcode.com/problems/missing-number/

- https://www.youtube.com/watch?v=-lfHWWMmXXM : Missing Smallest Positive Number

- Find the Duplicate Number (easy) : Input: [1, 4, 4, 3, 2]; Output: 4

This pattern describes an interesting approach to deal with problems involving arrays containing numbers in a given range. 
The Cyclic Sort pattern iterates over the array one number at a time, and if the current number you are iterating is not at the 
correct index, you swap it with the number at its correct index. You could try placing the number in its correct index, 
but this will produce a complexity of O(n^2) which is not optimal, hence the Cyclic Sort pattern.

**How do I identify this pattern?**
They will be problems involving a sorted array with numbers in a given range
If the problem asks you to find the missing/duplicate/smallest number in an sorted/rotated array


**Problems featuring cyclic sort pattern:**
- Find the Missing Number (easy)
- Find the Smallest Missing Positive Number (medium)

</details>

<details>
<summary> In-place reversal of linked list
</summary>

## In-place reversal of linked list

- file:///C:/Users/hmnsh/Documents/study/library/AlgoDs/EDUCAT~1.IO-/EDUCAT~1.IO-/7.%20Pattern%20In-place%20Reversal%20of%20a%20LinkedList/2.%20Reverse%20a%20LinkedList%20(easy)/1.1Reverse%20a%20LinkedList%20(easy)%20-%20Grokking%20the%20Coding%20Interview_%20Patterns%20for%20Coding%20Questions.html : Reverse a LinkedList (easy)

- file:///C:/Users/hmnsh/Documents/study/library/AlgoDs/EDUCAT~1.IO-/EDUCAT~1.IO-/7.%20Pattern%20In-place%20Reversal%20of%20a%20LinkedList/4.%20Reverse%20every%20K-element%20Sub-list%20(medium)/1.1%20Reverse%20every%20K-element%20Sub-list%20(medium)%20-.html : Reverse every K-element Sub-list (medium)

In a lot of problems, you may be asked to reverse the links between a set of nodes of a linked list. Often, 
the constraint is that you need to do this in-place, i.e., using the existing node objects and without using extra memory. 
This is where the above mentioned pattern is useful.
This pattern reverses one node at a time starting with one variable (current) pointing to the head of the linked list, 
and one variable (previous) will point to the previous node that you have processed. In a lock-step manner, 
you will reverse the current node by pointing it to the previous before moving on to the next node. 
Also, you will update the variable “previous” to always point to the previous node that you have processed.

**How do I identify when to use this pattern:**
If you’re asked to reverse a linked list without using extra memory


**Problems featuring in-place reversal of linked list pattern:**
- Reverse a Sub-list (medium)
- Reverse every K-element Sub-list (medium)

</details>




<details>
<summary> Subsets
</summary>

## Subsets

A huge number of coding interview problems involve dealing with Permutations and Combinations of a given set of elements. 
The pattern Subsets describes an efficient Breadth First Search (BFS) approach to handle all these problems.
The pattern looks like this:
Given a set of [1, 5, 3]
Start with an empty set: [[]]
Add the first number (1) to all the existing subsets to create new subsets: [[], [1]];
Add the second number (5) to all the existing subsets: [[], [1], [5], [1,5]];
Add the third number (3) to all the existing subsets: [[], [1], [5], [1,5], [3], [1,3], [5,3], [1,5,3]].


**How to identify the Subsets pattern:**  
Problems where you need to find the combinations or permutations of a given set


**Problems featuring Subsets pattern:**
- Subsets With Duplicates (easy)
- String Permutations by changing case (medium)

</details>

<details>
<summary> binary search
</summary>

## Binary Search
Whenever you are given a sorted array, linked list, or matrix, and are asked to find a certain element, the best algorithm you can use 
is the Binary Search. This pattern describes an efficient way to handle all problems involving Binary Search.
The patterns looks like this for an ascending order set:
First, find the middle of start and end. An easy way to find the middle would be: middle = (start + end) / 2. 
But this has a good chance of producing an integer overflow so it’s recommended that you represent the middle as: middle = start + (end — start) / 2
If the key is equal to the number at index middle then return middle
If ‘key’ isn’t equal to the index middle:
Check if key < arr[middle]. If it is reduce your search to end = middle — 1
Check if key > arr[middle]. If it is reduce your search to start = middle + 1

- https://www.youtube.com/watch?v=P3YID7liBug : Theory: HackerRank Binary Search

- https://www.youtube.com/watch?v=OAZc1zwjERU : Theory: Binary Search - Iterative Implementation and common errors

- https://www.topcoder.com/community/competitive-programming/tutorials/binary-search/

- https://www.youtube.com/watch?v=9BnC7orwkNA
- https://www.geeksforgeeks.org/painters-partition-problem-set-2/


**Problems featuring the Modified Binary Search pattern:**
- Order-agnostic Binary Search (easy)Search in a Sorted Infinite Array (medium)

- square root of a number : https://www.ideserve.co.in/learn/square-root-of-a-number

- Median of two sorted arrays : 
	- of same size : https://www.youtube.com/watch?v=MHNTl_NvOj0
	- of diff size : https://www.youtube.com/watch?v=LPFhl65R7ww

- Painter partition problem : https://www.youtube.com/watch?v=9BnC7orwkNA&t=1s

</details>

<details>
<summary> Top K elements
</summary>

##  Top K elements
Any problem that asks us to find the top/smallest/frequent ‘K’ elements among a given set falls under this pattern.
The best data structure to keep track of ‘K’ elements is Heap. This pattern will make use of the Heap to solve multiple problems 
dealing with ‘K’ elements at a time from a set of given elements. The pattern looks like this:
Insert ‘K’ elements into the min-heap or max-heap based on the problem.
Iterate through the remaining numbers and if you find one that is larger than what you have in the heap, then remove that 
number and insert the larger one.

There is no need for a sorting algorithm because the heap will keep track of the elements for you.


**How to identify the Top ‘K’ Elements pattern:**
If you’re asked to find the top/smallest/frequent ‘K’ elements of a given set
If you’re asked to sort an array to find an exact element


**Problems featuring Top ‘K’ Elements pattern:**
- Top ‘K’ Numbers (easy)
- Top ‘K’ Frequent Numbers (medium)

</details>

<details>
<summary> K-way Merge
</summary>

## K-way Merge
K-way Merge helps you solve problems that involve a set of sorted arrays.
Whenever you’re given ‘K’ sorted arrays, you can use a Heap to efficiently perform a sorted traversal of all the elements of all arrays. 
You can push the smallest element of each array in a Min Heap to get the overall minimum. After getting the overall minimum, 
push the next element from the same array to the heap. Then, repeat this process to make a sorted traversal of all elements.

**The pattern looks like this:**
Insert the first element of each array in a Min Heap.
After this, take out the smallest (top) element from the heap and add it to the merged list.
After removing the smallest element from the heap, insert the next element of the same list into the heap.
Repeat steps 2 and 3 to populate the merged list in sorted order.


**How to identify the K-way Merge pattern:**
The problem will feature sorted arrays, lists, or a matrix
If the problem asks you to merge sorted lists, find the smallest element in a sorted list.


**Problems featuring the K-way Merge pattern:**
- Merge K Sorted Lists (medium)
- K Pairs with Largest Sums (Hard)

</details>

<details>
<summary> Topological sort
</summary>

##  Topological sort
Topological Sort is used to find a linear ordering of elements that have dependencies on each other. For example, if event ‘B’ is dependent 
on event ‘A’, ‘A’ comes before ‘B’ in topological ordering.
This pattern defines an easy way to understand the technique for performing topological sorting of a set of elements.
The pattern works like this:
Initialization
a) Store the graph in adjacency lists by using a HashMap
b) To find all sources, use a HashMap to keep the count of in-degreesBuild the graph and find in-degrees of all vertices
Build the graph from the input and populate the in-degrees HashMap.
Find all sources
a) All vertices with ‘0’ in-degrees will be sources and are stored in a Queue.
Sort
a) For each source, do the following things:
—i) Add it to the sorted list.
— ii)Get all of its children from the graph.
— iii)Decrement the in-degree of each child by 1.
— iv)If a child’s in-degree becomes ‘0’, add it to the sources Queue.
b) Repeat (a), until the source Queue is empty.

**How to identify the Topological Sort pattern:**
The problem will deal with graphs that have no directed cycles
If you’re asked to update all objects in a sorted order
If you have a class of objects that follow a particular order


**Problems featuring the Topological Sort pattern:**
- Task scheduling (medium)
- Minimum height of a tree (hard)

</details>

<details>
<summary> Backtracking & Recursion
</summary>

## Backtracking & Recursion

Backtracking is the method of building the solution one piece at a time recursively and incrementally. 
The method keeps removing all those bits that do not contribute to the solution.

One such real-life example is a maze. At every dead end, you trace back your steps and set out for another path 
thus setting a perfect example for backtracking. Similarly, Sudoku works on the same principle.

That’s what backtracking is, re-tracing back the steps and discarding the choice that doesn't add on to build the correct solution.

### Recursion theory

- https://leetcode.com/explore/learn/card/recursion-i/250/principle-of-recursion/1439/ 

- https://www.youtube.com/watch?v=KEEKn7Me-ms : Algorithms: Recursion : hackerrank 

- https://www.youtube.com/watch?v=_OmRGjbyzno  : Recursion basics - using factorial

https://www.youtube.com/watch?v=ncpTxqK35PI  : Time and space complexity analysis of recursive programs - using factorial

https://www.youtube.com/watch?v=GM9sA5PtznY  : Why recursion is not always good

https://www.youtube.com/watch?v=pqivnzmSbq4  : Time Complexity analysis of recursion - Fibonacci Sequence

https://www.youtube.com/watch?v=dxyYP3BSdcQ  : Fibonacci Sequence - Anatomy of recursion and space complexity analysis

https://www.youtube.com/watch?v=KYH83T4q6Vs  : Reverse a linked list using recursion    

https://www.geeksforgeeks.org/modular-exponentiation-recursive/

https://byte-by-byte.wistia.com/medias/cwwyk06xhk?wvideo=cwwyk06xhk



### Backtracking theory

- https://unacademy.com/a/free-course-on-backtracking

https://www.interviewbit.com/courses/programming/topics/backtracking/

https://www.interviewbit.com/tutorial/backtracking/

https://www.interviewbit.com/tutorial/backtracking-pseudocode/



### Problem statements

- https://www.interviewbit.com/problems/subset/ 

- https://www.interviewbit.com/problems/permutations/

- https://www.geeksforgeeks.org/backtracking-approach-generate-n-bit-gray-codes/

- https://www.geeksforgeeks.org/printing-solutions-n-queen-problem/

- https://www.youtube.com/watch?v=xFv_Hl4B83A

</details>

<details>
<summary> Hashing
</summary>

## Hashing

- https://www.youtube.com/watch?v=shs0KM3wKv8&t=1s

- https://www.interviewbit.com/tutorial/introduction-to-hashing/

https://www.hackerearth.com/practice/data-structures/hash-tables/basics-of-hash-tables/tutorial/

### Interesting Problems

- https://www.interviewbit.com/problems/longest-substring-without-repeat/

- https://www.geeksforgeeks.org/count-maximum-points-on-same-line/

- https://www.geeksforgeeks.org/find-starting-indices-substrings-string-s-made-concatenating-words-listl/

- https://www.geeksforgeeks.org/longest-consecutive-subsequence/

- https://www.interviewbit.com/problems/distinct-numbers-in-window/

</details>

# Data Structures



<details>
<summary> Arrays
</summary>

## Arrays

- https://www.geeksforgeeks.org/longest-sub-array-sum-k/

- Binary Search
- Find Maximum in Sliding Window
- Search Rotated Array
- Find the Smallest Common Number
- Rotate Array
- Find Low/High index
- Move Zeros to the Left
- Find Maximum Single Sell Profit
- Implement Quicksort
- Merge Overlapping Intervals
- Sum of Two Values

**When to use** :

- Used as the building blocks to build other data structures such as array lists, heaps, hash tables, vectors and matrices.  
- Used for different sorting algorithms such as insertion sort, quick sort, bubble sort and merge sort.
</details>
<details>
<summary> Linked List
</summary>

## Linked List
https://www.interviewbit.com/courses/programming/topics/linked-lists/

- Array vs linkedlist : https://www.youtube.com/watch?v=lC-yYCOnN8Q
- find loop in a singly linkedlist https://www.geeksforgeeks.org/detect-and-remove-loop-in-a-linked-list/   
	https://www.ideserve.co.in/learn/detect-a-loop-in-a-linked-list 

- find merge pioint between 2 linked lists : https://www.youtube.com/watch?v=gE0GopCq378&t=65s

- Reverse a Singly Linked List : https://www.geeksforgeeks.org/reverse-a-linked-list/
- Remove Duplicates from a Linked List : https://www.geeksforgeeks.org/remove-duplicates-from-an-unsorted-linked-list/
- Delete Node with a Given Key : https://www.geeksforgeeks.org/delete-occurrences-given-key-linked-list/
- Insertion Sort of a Linked List : https://www.geeksforgeeks.org/insertion-sort-for-singly-linked-list/
- https://www.youtube.com/watch?v=sZ4uGB2HgOg : Basics of Linked List | Top Interview Problems Solved in Java - Part 1



- Nth from Last Node
- Swap Nth Node with Head
- Merge Two Sorted Linked Lists
- Merge Sort
- Reverse Even Nodes
- Rotate a Linked List
- Reverse k Elements
- Add Two Integers
- Copy Linked List with Arbitrary Pointer

</details>
<details>
<summary> String
</summary>

## String

- Reverse Words in a Sentence
- Remove Duplicates
- Remove White Spaces
- String Segmentation
- XML to Tree
- Find all Palindrome Substrings
- Regular Expression

- https://www.youtube.com/watch?v=qQ8vS2btsxI : Rabin-Karp String Matching Algorithm

</details>
<details>
<summary> Stacks and Queues
</summary>

## Stacks and Queues
- Stack Using Queues
- Queue Using Stacks
- Expression Evaluation

### Stack tutorial videos
https://www.youtube.com/watch?v=F1F2imiOJfk : Theory [MANDATORY] Data structures: Introduction to stack : mycodeschool

- https://www.youtube.com/watch?v=wjI1WNcIntg [MANDATORY] : HackerRank

https://www.youtube.com/watch?v=m4hvxzLoN_I Monotonic stack
- https://leetcode.com/contest/biweekly-contest-28/problems/final-prices-with-a-special-discount-in-a-shop/
- https://leetcode.com/problems/daily-temperatures/

https://www.hackerearth.com/practice/data-structures/stacks/basics-of-stacks/tutorial/

https://www.youtube.com/watch?v=sFVxsglODoo : Array implementation of stacks [MANDATORY]

https://www.youtube.com/watch?v=MuwxQ2IB8lQ : Linked List implementation of stacks [MANDATORY]

https://www.youtube.com/watch?v=hNP72JdOIgY : Reverse a string or linked list using stack. [optional]

https://www.youtube.com/watch?v=QZOLb0xHB_Q : Check for balanced parentheses using stack [optional]

### Stack interesting problem

- problem : https://www.interviewbit.com/problems/evaluate-expression/ [Difficult]
	- solution : https://github.com/himkak/interviewbit/blob/master/src/com/interviewbit/stacksandqueues/EvaluateExpression.java

- problem : https://www.interviewbit.com/problems/min-stack/
	- https://www.youtube.com/watch?v=WxCuL3jleUA
	- solution : https://github.com/himkak/interviewbit/blob/master/src/com/interviewbit/stacksandqueues/MinStack.java

- problem : https://www.interviewbit.com/problems/nearest-smaller-element/
	- solution : https://github.com/himkak/interviewbit/blob/master/src/com/interviewbit/stacksandqueues/NearestSmallestElement.java
	
- https://www.youtube.com/watch?v=VNbkzsnllsU&list=PLq9MXGH7Fkt-jNNDHsuMIPFHsYBfD4LrZ&index=15&t=606s : Coding Interview Problem: Largest Rectangle in a Histogram

- https://www.interviewbit.com/problems/evaluate-expression/ : Reverse Polish Notation.

#### Monotonic Stacks

- When ever we have to find the next smaller or bigger to the right or left, we use monotonic stack.

- https://www.youtube.com/watch?v=TunTV2-griM

- https://www.youtube.com/watch?v=sDKpIO2HGq0
- https://www.youtube.com/watch?v=8BDKB2yuGyg
- https://www.ideserve.co.in/learn/next-great-element-in-an-array

- If we have to find smaller to right, we traverse left to right.  
Since we have to find smaller so we have to create monotonic increasing stack (smaller to bigger).

```
public int[] findSmallerToRight(int[] input){
	int[] res= new int[input.length];
	Stack<Integer> st=new Stack<>();
	
	for(int i=0;i<input.length;i++){
	//since it is increasing stack, so we remove the bigger elems from stack.
	while(!st.isEmpty() && input[i] < input[st.peek()]){
		st.pop();
		//which ever elem removes the elem from stack that is the next smaller elem, for that elem removed from stack.
		res[st.peek()]=i;
	}
	st.add(i);
	res[i]=-1;
	}
	
	return res;
}
```


- If we have to find smaller to the left, we traverse right to left.  
Since we have to find smaller so again we have to create monotonic increasing stack.


-If we have to find larger to the right, we traverse left to right.  
Since we have to find larger, so we create monotonic decreasing stack.



- **Summary** : move towards the direction in which we have to find the next elem.  
Make opposite monotonic stack of what u have to find. If we have to find smaller, create increasing stack, if we have to find bigger, then we create decreasin stack.


Eg : https://leetcode.com/explore/learn/card/queue-stack/230/usage-stack/1363/ : Daily Temperatures

### Queue

- https://www.youtube.com/watch?v=XuCbpw6Bj1U : Data structures: Introduction to Queues [MANDATORY]

- https://www.youtube.com/watch?v=okr-XE8yTO8 : Data structures: Array implementation of Queue [MANDATORY]

- https://www.youtube.com/watch?v=A5_XdiK4J8A : Data structures: Linked List implementation of Queue [MANDATORY]

- https://www.hackerearth.com/practice/data-structures/queues/basics-of-queues/tutorial/

#### Queue for BFS

- BFS : https://leetcode.com/explore/learn/card/queue-stack/231/practical-application-queue/1376/
- BFS Template : https://leetcode.com/explore/learn/card/queue-stack/231/practical-application-queue/1372/
- https://leetcode.com/explore/learn/card/queue-stack/231/practical-application-queue/1371/ : uses queue and BFS
- https://leetcode.com/problems/word-ladder/ 

- https://unacademy.com/a/free-course-on-stack-and-queues : stacks and queues : unacademy

#### Queues & Stacks most frequently asked questions
- https://leetcode.com/explore/learn/card/queue-stack/239/conclusion/1386/ : Implement Queue using Stacks
- 

</details>

<details>
<summary> Pattern Matching
</summary>

## Pattern Matching

### Rabin karp
- https://www.youtube.com/watch?v=qQ8vS2btsxI&t=36s

### Knuth-Morris-Pratt KMP String Matching Algorithm
- https://www.youtube.com/watch?v=V5-7GzOfADQ

</details>

<details>
<summary> Tree
</summary>

## Tree

- https://www.youtube.com/watch?v=qH6yxkw0u78 : Data structures: Introduction to Trees [Beginner]

- https://www.youtube.com/watch?v=oSWTXtMglKE : Data Structures: Trees [Mandatory]

- https://www.youtube.com/watch?v=TQI_m32_AeU : Find the Maximum Depth or Height of a Tree | GeeksforGeeks [Mandatory]



### Binary Tree

**A binary tree is a tree with exactly two sub-trees for each node, called the left and right sub-trees.**

- https://www.youtube.com/watch?v=H5JubkIy_p8 : Data structures: Binary Tree

- https://www.geeksforgeeks.org/binary-tree-data-structure/

**Strict binary tree**
If every node has either 2 or 0 children.

**Complete binary Tree**
If all levels except the last level are completely filled.

**Perfect Binary tree**
All levels will be completely filled

#### Good problems

- https://www.geeksforgeeks.org/construct-tree-from-given-inorder-and-preorder-traversal/ [Mandatory]
- create binary tree from inorder and postorder traversal : https://www.youtube.com/watch?v=s5XRtcud35E [Mandatory]

- https://www.geeksforgeeks.org/check-if-given-preorder-inorder-and-postorder-traversals-are-of-same-tree/

- https://www.youtube.com/watch?v=G46cenlnXvI : Populate next right pointers in a binary tree

- https://www.youtube.com/watch?v=13m9ZCB8gjw : Lowest Common Ancestor Binary Tree : solution is a pre-order traversal


### Binary Search Tree

**A binary search tree is a binary tree where, for each node m,the left sub-tree only has nodes with keys smaller than (according to some total order) the key of m,while the right sub-tree only has nodes with keys larger than the key of m.**

- https://leetcode.com/explore/learn/card/data-structure-tree/17/solve-problems-recursively/534/ 

- https://www.geeksforgeeks.org/tree-traversals-inorder-preorder-and-postorder/

- https://www.youtube.com/watch?v=pYT9F8_LFTM : Data structures: Binary Search Tree

- https://www.interviewbit.com/tutorial/binary-search-tree/

- https://www.youtube.com/watch?v=COZK7NATh4k : Binary search tree - Implementation in C/C++

- https://www.youtube.com/watch?v=gcULXE7ViZw : Delete a node in BST


![BST Comparison with other DS](https://github.com/himkak/notes/blob/master/AlgoDS/BSTComparison.PNG)

### Balanced Tree

**A balanced tree is a tree where every leaf is “not more than a certain distance” away from the root than any other leaf**

### Types of Balanced Tress

#### Red Black Tree

#### AVL Tree

### Tree Traversal

- https://www.youtube.com/watch?v=9RHO6jU--GU : Binary tree traversal - breadth-first and depth-first strategies

- https://leetcode.com/explore/learn/card/data-structure-tree/134/traverse-a-tree/992/

- https://www.geeksforgeeks.org/bfs-vs-dfs-binary-tree/

- https://towardsdatascience.com/4-types-of-tree-traversal-algorithms-d56328450846



#### BFS

- https://www.youtube.com/watch?v=86g8jAQug04

- file:///C:/Users/hmnsh/Documents/study/library/AlgoDs/EDUCAT~1.IO-/EDUCAT~1.IO-/8.%20Pattern%20Tree%20Breadth%20First%20Search/6.%20Minimum%20Depth%20of%20a%20Binary%20Tree%20(easy)/1.1Minimum%20Depth%20of%20a%20Binary%20Tree%20(easy)%20-.html : Minimum Depth of a Binary Tree (easy)

- file:///C:/Users/hmnsh/Documents/study/library/AlgoDs/EDUCAT~1.IO-/EDUCAT~1.IO-/8.%20Pattern%20Tree%20Breadth%20First%20Search/8.%20Connect%20Level%20Order%20Siblings%20(medium)/1.1Connect%20Level%20Order%20Siblings%20(medium)%20-.html : Connect Level Order Siblings (medium)

- file:///C:/Users/hmnsh/Documents/study/library/AlgoDs/EDUCAT~1.IO-/EDUCAT~1.IO-/8.%20Pattern%20Tree%20Breadth%20First%20Search/12.%20Solution%20Review%20Problem%20Challenge%202/1.1Solution%20Review_%20Problem%20Challenge%202%20-.html : Right View of a Binary Tree (easy) 


This pattern is based on the Breadth First Search (BFS) technique to traverse a tree and uses a queue to keep track of 
all the nodes of a level before jumping onto the next level. Any problem involving the traversal of a tree in a level-by-level 
order can be efficiently solved using this approach.
The Tree BFS pattern works by pushing the root node to the queue and then continually iterating until the queue is empty. 
For each iteration, we remove the node at the head of the queue and “visit” that node. After removing each node from the queue, 
we also insert all of its children into the queue.


**How to identify the Tree BFS pattern:**
If you’re asked to traverse a tree in a level-by-level fashion (or level order traversal)


**Problems featuring Tree BFS pattern:**
- Binary Tree Level Order Traversal (easy)
- Zigzag Traversal (medium)

#### DFS

- https://www.geeksforgeeks.org/depth-first-search-or-dfs-for-a-graph/

- https://www.hackerearth.com/practice/algorithms/graphs/depth-first-search/tutorial/

- file:///C:/Users/hmnsh/Documents/study/library/AlgoDs/EDUCAT~1.IO-/EDUCAT~1.IO-/9.%20Pattern%20Tree%20Depth%20First%20Search/2.%20Binary%20Tree%20Path%20Sum%20(easy)/1.1Binary%20Tree%20Path%20Sum%20(easy)%20-%20Grokking%20the%20Coding%20Interview_%20Patterns%20for%20Coding%20Questions.html : Binary Tree Path Sum (easy)

- Check if Two Binary Trees are Identical  
- Write an In-Order Iterator for a Binary Tree  
- Iterative Inorder Traversal  
- Inorder Successor BST  
- Level Order Traversal of Binary Tree  
- Is Binary Search Tree?  
- Convert Binary Tree to Doubly Linked List  
- Print Tree Perimeter  
- Connect Same Level Siblings  
- Serialize/Deserialize Binary Tree  
- Connect All Siblings   
- Inorder Successor BST with Parent Pointers  
- Nth Highest in BST  
- Mirror Binary Tree Nodes  
- Delete Zero Sum Sub-Trees  
- N-ary Tree to Binary Tree  



Tree DFS is based on the Depth First Search (DFS) technique to traverse a tree.
You can use recursion (or a stack for the iterative approach) to keep track of all the previous (parent) nodes while traversing.
The Tree DFS pattern works by starting at the root of the tree, if the node is not a leaf you need to do three things:
Decide whether to process the current node now (pre-order), or between processing two children (in-order) or after processing 
both children (post-order).
Make two recursive calls for both the children of the current node to process them.


**How to identify the Tree DFS pattern:**
If you’re asked to traverse a tree with in-order, preorder, or postorder DFS
If the problem requires searching for something where the node is closer to a leaf


**Problems featuring Tree DFS pattern:**
- Sum of Path Numbers (medium)
- All Paths for a Sum (medium)


**Find the lowest common ancestor of two leafs nodes** using eulerian path method
- https://www.youtube.com/watch?v=sD1IoalFomA&list=PLDV1Zeh2NRsDGO4--qE8yH72HFL1Km93P&index=13

##### In-Order Traversal
In-order traversal means to "visit" (often, print) the left branch, then the current node, and finally, the right
branch.

``` 
void inOrderTraversal(TreeNode node) {
	if (node != null) {
	inOrderTraversal(node.left);
	visit(node);
	inOrderTraversal(node.right);
	}
 }
 ```
When performed on a binary search tree, it visits the nodes in ascending order (hence the name "in-order").

- https://www.youtube.com/watch?v=VCTP81Ij-EM : Create a balanced Binary Search Tree (BST) from a sorted array

- https://www.interviewbit.com/problems/inorder-traversal/

##### Pre-Order Traversal
Pre-order traversal visits the current node before its child nodes (hence the name "pre-order").
```
void preOrderTraversal(TreeNode node) {
	if (node != null) {
	visit(node);
	inOrderTraversal(node.left);
	inOrderTraversal(node.right);
	}
 }
```
In a pre-order traversal, the root is always the first node visited.

##### Post-Order Traversal
Post-order traversal visits the current node after its child nodes (hence the name "post-order").
```
void postOrderTraversal(TreeNode node) {
	if (node != null) {
	inOrderTraversal(node.left);
	inOrderTraversal(node.right);
	visit(node);
	}
 }
```
In a post-order traversal, the root is always the last node visited.


### Fenwick tree
- Also called **Binary index tree**

- https://www.youtube.com/watch?v=RgITNht_f4Q&list=PLDV1Zeh2NRsB6SWUrDFW2RmDotAfPbeHu&index=38


</details>




<details>
<summary> Graphs
</summary>

## Graphs

### References

- https://www.youtube.com/playlist?list=PLq9MXGH7Fkt9bh69QxtMXPbdfL57qPbYq : My Graph playlist, with all liked videos in learning order
- https://leetcode.com/discuss/general-discussion/969327/Graph-Algorithms-One-Place-or-Dijkstra-or-Bellman-Ford-or-Floyd-Warshall-or-Prims-or-Kruskals-or-DSU 
- https://www.hackerearth.com/practice/algorithms/graphs/graph-representation/tutorial/

- https://www.interviewbit.com/courses/programming/topics/graph-data-structure-algorithms/

- https://www.youtube.com/watch?v=gXgEDyodOJU : Data structures: Introduction to graphs

- https://www.youtube.com/watch?v=AfYqN3fGapc : Data structures: Properties of Graphs

- https://www.interviewbit.com/tutorial/breadth-first-search/

- https://www.interviewbit.com/tutorial/depth-first-search/

- C:\Users\hmnsh\Documents\study\library\AlgoDs\Educative.io - Grokking the Coding Interview - Patterns for Coding Questions\Educative.io - Grokking the Coding Interview - Patterns for Coding Questions\17. Pattern Topological Sort (Graph)

- https://www.youtube.com/playlist?list=PLDV1Zeh2NRsDGO4--qE8yH72HFL1Km93P : Graph and Tree Tutorials by a Google Dev

- https://leetcode.com/discuss/general-discussion/655708/graph-for-beginners-problems-pattern-sample-solutions/562734 : practise|  problems separated add to graph sub topic wise

- https://leetcode.com/discuss/general-discussion/655708/Graph-For-Beginners-Problems-or-Pattern-or-Sample-Solutions


### Representation

- https://www.khanacademy.org/computing/computer-science/algorithms/graph-representation/a/representing-graphs

- https://www.youtube.com/watch?v=5hPfm_uqXmw : Graph representation in Data Structure(Graph Theory)|Adjacency Matrix and Adjacency List

- https://www.youtube.com/watch?v=WQ2Tzlxl_Xo

#### Adjacency Matrix

- space complexity : O(n^2)
- good for dense graph

#### Adjacency List

- space complexity : O(n + e)     [2e since every edge is written 2 times]
- good for sparse graph

### Traversal

- https://www.youtube.com/watch?v=zaBhtODEL0w : Hackerrank Algorithms: Graph Search, DFS and BFS By Gayle Laakmann McDowell
Note : To find shortest path between 2 nodes use BFS

- https://leetcode.com/explore/learn/card/data-structure-tree/134/traverse-a-tree/

#### BFS

- used to find the shortest path
- To create the path, same prev of every node and then from destination move to src.

- runtime complexity : O(V+E)

- https://youtu.be/ls4cHglfc0g : BFS

- https://www.youtube.com/watch?v=pyNl0ESkH24

- https://www.youtube.com/watch?v=ZVJFOrsHxMs : Breadth-first Search (BFS) on Graphs Part 2 - Implementation

- https://www.youtube.com/watch?v=KiCBXu4P-2Y : Breadth First Search grid shortest path | Graph Theory



#### DFS

- https://youtu.be/fI6X6IBkzcw


#### Graph Coloring

- https://www.youtube.com/watch?v=052VkKhIaQ4

**Bipartite Graph**

- https://www.youtube.com/watch?v=mVmXwFkgoJ0
- https://www.youtube.com/watch?v=0ACfAqs8mm0

- https://www.youtube.com/watch?v=GhjwOiJ4SqU
- https://www.youtube.com/watch?v=LdOnanfc5TM

**Chromatic value**
- Minimum number of colors requred to color graph, so that no 2 connected edges have same color.

### Check if Graph has cycle

- https://www.youtube.com/watch?v=joqmqvHC_Bo

- https://leetcode.com/problems/course-schedule/ : problem with solution

#### Tarjan's Strongly connected components Algo
- https://www.youtube.com/watch?v=wUgWX0nc4NY&t=384s

### Topological Sort

In computer science, a topological sort or topological ordering of a directed graph is a linear ordering of its vertices such that for every directed edge uv from vertex u to vertex v, u comes before v in the ordering. For instance, the vertices of the graph may represent tasks to be performed, and the edges may represent constraints that one task must be performed before another; in this application, a topological ordering is just a valid sequence for the tasks. A topological ordering is possible if and only if the graph has no directed cycles, that is, if it is a directed acyclic graph (DAG). Any DAG has at least one topological ordering, and algorithms are known for constructing a topological ordering of any DAG in linear time.

Eg : Suppose I have to do some courses, and every course has some prerequisites courses. So now i want to know what is the order of executing courses or info around it. So we can use topological sort.

- https://www.youtube.com/watch?v=eL-KzMXSXXI&list=PLDV1Zeh2NRsDGO4--qE8yH72HFL1Km93P&index=15 : Theory

- https://leetcode.com/problems/course-schedule-ii/



### Shortest Path Algos:

https://www.hackerearth.com/practice/algorithms/graphs/shortest-path-algorithms/tutorial/



#### Shortest path in a grid

- https://www.youtube.com/watch?v=KiCBXu4P-2Y : Breadth First Search grid shortest path | Graph Theory

#### Single Source Shortest Path

- https://www.youtube.com/watch?v=TXkDpqjDMHA&list=PLDV1Zeh2NRsDGO4--qE8yH72HFL1Km93P&index=16 : Shortest/Longest path on a Directed Acyclic Graph (DAG) | Graph Theory

- https://www.youtube.com/watch?v=ePqBaDRHkdk&list=PLSVu1-lON6LyvJV6EwIJrcZi4ONJmQCQ5&index=4

- start by setting all the distances between source and all the nodes as infinity, except from source to source which will be 0
- In this algo, we first do topological sort and then pick the next node acc to topological sort, and update the distance if value is less than existing.

#### Dijkstra's Algorithm

- Greedy Algo

- Used to find the cost of shortest path from a source to a destination node, in a weighted graph. 
- provides shortest path from one node to all other nodes
- **Similar to BFS but Uses priority Queue instead of queue.**
- once all the neighbours of the node are loaded into priority queue, the node is moved to processed. Every time while picking a node, we check if the node is processed, if so skip it.

	- https://www.youtube.com/watch?v=GazC3A4OQTE : Dijkstra's Algorithm - Computerphile (****)
	
	- https://www.youtube.com/watch?v=DAj7mtiAiQM : Dijkstra's Algorithm for Shortest Path Problem with Example in Hind/English (**)

	- https://www.youtube.com/watch?v=d6ZFqjH63vo : How to use Dijkstra's Algorithm with Code (*)

	- https://youtu.be/ba4YGd7S-TY : Dijkstra’s shortest path algorithm | GeeksforGeeks

	- https://www.geeksforgeeks.org/dijkstras-shortest-path-algorithm-greedy-algo-7/

	- https://www.geeksforgeeks.org/printing-paths-dijkstras-shortest-path-algorithm/
	
	- https://www.youtube.com/watch?v=pSqmAO-m7Lk&list=PLDV1Zeh2NRsDGO4--qE8yH72HFL1Km93P&index=17 : Dijkstra's Shortest Path Algorithm | Graph Theory  (****)
	
**Problems**
- No importance given to the direction, inspite we might be traversing in the opposite direction but destination node is in the opposite direction.

#### Bellman Ford's Algorithm
- Single source shortest path
- Dijstra doesnt works for -ve weighted graph

- https://www.youtube.com/watch?v=FtN3BYH2Zes

- https://www.youtube.com/watch?v=obWXjtg0L64

#### Floyd–Warshall's Algorithm

- Used to find the cost of shortest path from each vertex to every other vertex. Also called **All Pair shortest path** (APSP)
- shortest path between all pairs of vertces, -ve path allowed

- https://www.youtube.com/watch?v=4OQeCuLYj-4

#### A* (A Start)

- https://www.youtube.com/watch?v=ySN5Wnu88nE



### Minimum Spanning tree :

The cost of the spanning tree is the sum of the weights of all the edges in the tree. There can be many spanning trees. Minimum spanning tree is the spanning tree where the cost is minimum among all the spanning trees. There also can be many minimum spanning trees.

- no of spanning trees possible from a graph = (noOfEdges)* (noOfEdges - noOfVertices) - no of cycles in the graph

- Minimum spanning tree is created by using greedy algorithm. You select the vertex with minimum weight, if it connects to unvisited edge.

- If each edge has distinct weight, there is only one MST possible

- Disconnected graphs doesnt contains any Spanning Tree

- https://www.youtube.com/watch?v=4ZlRH0eK-qQ

- https://www.hackerearth.com/practice/algorithms/graphs/minimum-spanning-tree/tutorial/ : minimum spanning tree

- https://www.geeksforgeeks.org/prims-minimum-spanning-tree-mst-greedy-algo-5/ : Minimum spanning tree 

- https://www.youtube.com/watch?v=vNhvBrc02G4

#### Prim's

- first, select the minimum cost edge from the graph.
- Then select the minimum cost edge from the graph, but it should be connected to the previous one.
- Use min priority queue

![Minimum spanning tree Prim's Lazy Algo](https://github.com/himkak/notes/blob/master/AlgoDS/graph/MinSpanningTree_PrimsLazyAlgo.JPG)

- https://www.youtube.com/watch?v=jsmMtJpPnhU : Prim's Minimum Spanning Tree Algorithm | Graph Theory

- step 1: Start from a node Iterate all the edges of the node and add them to min priority queue. Priority queue is of type T(start, end, cost). priority queue is sorted acc to cost (min-max). Mark the node as visited.
- step 2: pull the first T from priority queue, check if both of its nodes are not visited, if visited skip it, else, add it to MST, and this will be next node to visit. Add all its edges to min priority queue, dont add any node which is already visited. Mark this node as visited.

- as soon as we find no of edges = no of nodes -1, we have the MST

## Kruskal's

- Always select the minimum cost edge. But if it is creating a cycle in the graph, dont include it.











- Clone a Directed Graph  
- Minimum Spanning Tree  
- Word Chaining  
- Back Tracking  
- Boggle  
- All Possible Braces  
- Solve N-Queens Problem  
- Find K-Sum Subsets  

</details>

<details>
<summary> Greedy Algorithm
</summary>

## Greedy Algorithm

- https://www.interviewbit.com/tutorial/greedy-algorithm-introduction/

- https://www.youtube.com/watch?v=ARvQcqJ_-NY

- https://www.youtube.com/watch?v=co4_ahEDCho : Huffman coding, to compress a string

- https://www.youtube.com/watch?v=tKwnms5iRBU&t=690s : MIT Greedy Algorithms: Minimum Spanning Tree

### Properties of greedy problem
- Optimal substructure: If you can solve the subproblem optimally then you can solve the probelm also optimally
- greedy choice property : locally optimal choices lead to globally optimal solution

</details>

<details>
<summary> Dynamic Programming
</summary>

## Dynamic Programming
- Fibonacci Numbers  
- Largest Sum Subarray  
- MaxSum Subsequence - Nonadjacent Elements  
- Combinations for Game Scoring  
- Coin Changing Problem  
- Levenshtein Distance  

### Definition
 If you have solved a problem with the given input, then save the result for future reference, so as to avoid solving the same problem again.. shortly 'Remember your Past' :) .  If the given problem can be broken up in to smaller sub-problems and these smaller subproblems are in turn divided in to still-smaller ones, and in this process, if you observe some over-lapping subproblems, then its a big hint for DP. Also, the optimal solutions to the subproblems contribute to the optimal solution of the given problem ( referred to as the Optimal Substructure Property ).
 
 
 Note that divide and conquer is slightly a different technique. In that, we divide the problem in to non-overlapping subproblems and solve them independently, like in mergesort and quick sort.
 
 
 The intuition behind dynamic programming is that we trade space for time, i.e. to say that instead of calculating all the states taking a lot of time but no space, we take up space to store the results of all the sub-problems to save time later.

- https://www.youtube.com/playlist?list=PLVrpF4r7WIhTT1hJqZmjP10nxsmrbRvlf  : playlist for basics
- https://www.codechef.com/wiki/tutorial-dynamic-programming : code chef tutorial
- https://www.hackerearth.com/practice/notes/dynamic-programming-i-1/ 
- https://leetcode.com/discuss/general-discussion/458695/Dynamic-Programming-Patterns


- https://en.wikipedia.org/wiki/Dynamic_programming
- https://algorithmist.com/wiki/Longest_increasing_subsequence
- https://www.topcoder.com/community/competitive-programming/tutorials/dynamic-programming-from-novice-to-advanced/
- https://www.youtube.com/channel/UClnwNEngsXoIp_tgJ2jZWfw
- https://leetcode.com/discuss/general-discussion/458695/dynamic-programming-patterns : famous leetcode page

- https://leetcode.com/discuss/general-discussion/491522/Dynamic-Programming-Questions-Thread?fbclid=IwAR1jQGU1Ox3_omZ_n7wdYfVM1Z7E3XyQDmTlJ0YNNcVLZrlHFBevvxM0g2o : list of famous DP questions

- https://coursehunters.online/t/the-interview-cake-course-6-dynamic-programming-and-recursion/3183

- Egg Drop :  https://www.youtube.com/watch?v=iOaRjDT0vjc

- https://www.youtube.com/watch?v=P8Xa2BitN3I : Algorithms: Memoization and Dynamic Programming | hackerrank

- https://www.interviewbit.com/tutorial/dynamic-programming-dp-introduction/ 

- https://www.geeksforgeeks.org/dynamic-programming/

- https://www.geeksforgeeks.org/find-length-longest-subsequence-one-string-substring-another-string/

- https://www.hackerearth.com/practice/algorithms/dynamic-programming/introduction-to-dynamic-programming-1/tutorial/

- Maximum Subarray Problem : https://medium.com/@rsinghal757/kadanes-algorithm-dynamic-programming-how-and-why-does-it-work-3fd8849ed73d

- https://www.youtube.com/watch?v=xhod_0DxkNM : Longest Common Subsequence

- https://www.youtube.com/watch?v=CE2b_-XfVDk : longest increasing subsequence

- https://leetcode.com/discuss/general-discussion/662866/Dynamic-Programming-for-Practice-Problems-Patterns-and-Sample-Solutions : Practise | DP questions sub topics wise


### Types of DP problems
1. Combinatorics : In these kind of problems we have to find the no of ways. 
	- Eg : No of way to climb n stairs when you can take 1 to k steps at a time.
2. Optimization : IN this kind of problem we have to find the min / max / best / worst.
	- Eg : Find the minumum price to reach the top of the stairs

### Steps to solve 
1. Define the objective function
2. Identify the base case
3. Write the recurrence relation for the optimized objective function. f(n)= ?
4. what is the order of execution
5. Where to look for the answer



![Dp Framework](https://github.com/himkak/notes/blob/master/AlgoDS/DP/DpFrameworkWithSampleSolution.JPG)

#### Eg 1: Jump Game
- https://leetcode.com/articles/jump-game/

</details>

<details>
<summary> Heap
</summary>

## Heap

- https://www.youtube.com/playlist?list=PLSVu1-lON6Lwqj5nDqg8YyD7f4tjLMMBN

- https://www.interviewbit.com/tutorial/heap-and-map-implementation-details/

- https://www.interviewbit.com/tutorial/why-treemaps-heaps

- https://www.geeksforgeeks.org/heap-data-structure/

- https://www.youtube.com/watch?v=t0Cq6tVNRBA

- https://www.youtube.com/watch?v=HqPJF2L5h9U&t=870s

- https://en.wikipedia.org/wiki/Heap_%28data_structure%29

- https://www.youtube.com/watch?v=wptevk0bshY&list=PLDV1Zeh2NRsB6SWUrDFW2RmDotAfPbeHu&index=14 : Priority Queue Introduction


![Heap In Array](https://github.com/himkak/notes/blob/master/AlgoDS/HeapInArray.PNG)

### Good Problems

- https://www.geeksforgeeks.org/merge-k-sorted-arrays/
- https://www.interviewbit.com/problems/distinct-numbers-in-window/
- https://www.geeksforgeeks.org/find-k-closest-numbers-in-an-unsorted-array/

## Two heaps
In many problems, we are given a set of elements such that we can divide them into two parts. 
To solve the problem, we are interested in knowing the smallest element in one part and the biggest element in the other part. 
This pattern is an efficient approach to solve such problems.
This pattern uses two heaps; A Min Heap to find the smallest element and a Max Heap to find the biggest element. 
The pattern works by storing the first half of numbers in a Max Heap, this is because you want to find the largest number in the first half. 
You then store the second half of numbers in a Min Heap, as you want to find the smallest number in the second half. 
At any time, the median of the current list of numbers can be calculated from the top element of the two heaps.


**Ways to identify the Two Heaps pattern:**  
Useful in situations like Priority Queue, Scheduling
If the problem states that you need to find the smallest/largest/median elements of a set
Sometimes, useful in problems featuring a binary tree data structure


**Problems featuring**  
Find the Median of a Number Stream (medium)


### Min Heap

A min-heap is a complete binary tree (that is, totally filled other than the rightmost elements on the last level) where each node is smaller than its children. The root, therefore, is the minimum element in the tree.

**Insertion into and deletion from a heap**
- https://www.geeksforgeeks.org/insertion-and-deletion-in-heaps/

- https://www.geeksforgeeks.org/kth-smallestlargest-element-unsorted-array/

- https://www.youtube.com/watch?v=WCm3TqScBM8

#### store heap in array

For zero based array
- index of left child of i = 2*i + 1
- index of right child of i = 2*i + 2
- parent = (i-1)/2


#### Insert

![Insert into min heap](https://github.com/himkak/notes/blob/master/AlgoDS/InsertIntoMinHeap.PNG)

#### Remove root node from minHeap

![Delete root node from min heap](https://github.com/himkak/notes/blob/master/AlgoDS/DeleteFromMinHeap.PNG)


### Max Heap


- https://www.youtube.com/watch?v=WsNQuCa_-PU

- https://www.interviewbit.com/problems/n-max-pair-combinations/

- https://www.geeksforgeeks.org/number-ways-form-heap-n-distinct-integers/

</details>


<details>
<summary> Trie
</summary>



## Trie

![Trie](https://github.com/himkak/notes/blob/master/AlgoDS/Trie.PNG)

- https://www.youtube.com/watch?v=zIjfhVPRZCg&t=7s : Data Structures: Tries : Hackerrank

- https://www.geeksforgeeks.org/find-all-shortest-unique-prefixes-to-represent-each-word-in-a-given-list/

- https://leetcode.com/discuss/general-discussion/680706/article-on-trie-general-template-and-list-of-problems




</details>

<details>
<summary> Union Find
</summary>

## Union Find

- Also known as disjoint set

- https://www.youtube.com/watch?v=ibjEGG7ylHk : Union Find Introduction

- https://leetcode.com/discuss/general-discussion/655708/graph-for-beginners-problems-pattern-sample-solutions/562734 : questions to practise and template of code

![Complexity](https://github.com/himkak/notes/blob/master/AlgoDS/unionFind/Complexity.JPG)

- https://www.youtube.com/watch?v=0jNmHPfA_yE : Union Find - Union and Find Operations

- https://www.youtube.com/watch?v=VHRhJWacxis : Union Find Path Compression

- https://www.youtube.com/watch?v=KbFlZYCpONw : Union Find Code

- https://www.youtube.com/watch?v=ID00PMy0-vE : Disjoint Sets using union by rank and path compression Graph Algorithm

- https://www.youtube.com/watch?v=wU6udHRIkcc : 1.12 Disjoint Sets Data Structure - Weighted Union and Collapsing Find

- https://leetcode.com/problems/friend-circles/discuss/101336/Java-solution-Union-Find : Union Find Template | Frields circle solution

### Algo

#### variables

- parent[] : size is no of elems. In init set every elem parent as itself
- rank[] : size is no of elems
- count : no of elems

#### Operations

- initialize : takes input as no of elems. Initialize all the variables

- union : It takes input as 2 values and creates a union of both.
			Find the parent of p, find the parent of q
			Check which set is smaller, by using rank
			set parent[parentSmaller]= parentBigger
			If both sets are of same rank, increase the rank of parrentBigger by 1
			
- find : find the parent of the node. In other words, find the root of the set it belongs to.
			while node doesnt points to itslef, keep on moving up.
			
### Examples

#### Friend circles 

```
public class Solution {
    class UnionFind {
        private int count = 0;
        private int[] parent, rank;
        
        public UnionFind(int n) {
            count = n;
            parent = new int[n];
            rank = new int[n];
            for (int i = 0; i < n; i++) {
                parent[i] = i;
            }
        }
        
        public int find(int p) {
        	while (p != parent[p]) {
                parent[p] = parent[parent[p]];    // path compression by halving
                p = parent[p];
            }
            return p;
        }
        
        public void union(int p, int q) {
            int rootP = find(p);
            int rootQ = find(q);
            if (rootP == rootQ) return;
            if (rank[rootQ] > rank[rootP]) {
                parent[rootP] = rootQ;
            }
            else {
                parent[rootQ] = rootP;
                if (rank[rootP] == rank[rootQ]) {
                    rank[rootP]++;
                }
            }
            count--;
        }
        
        public int count() {
            return count;
        }
    }
    
    public int findCircleNum(int[][] M) {
        int n = M.length;
        UnionFind uf = new UnionFind(n);
        for (int i = 0; i < n - 1; i++) {
            for (int j = i + 1; j < n; j++) {
                if (M[i][j] == 1) uf.union(i, j);
            }
        }
        return uf.count();
    }
}

```

### Kruskal's minimum spanning tree

- https://www.youtube.com/watch?v=JZBQLXgSGfs

![Algo](https://github.com/himkak/notes/blob/master/AlgoDS/unionFind/KruskalsMinimumSpanningTree.JPG)

### Least common ancestor in tree



</details>

<details>
<summary> Miscellaneous
</summary>

## Miscellaneous
- Sum of Three Values  
- Make Columns and Rows Zeros  
- Search in a Matrix  
- Implement LRU Cache  
- Host Endianness  
- Closest Meeting Point  


</details>



<details>
<summary> Generic Steps to solve any algo problem
</summary>

# How to approach coding interviews

1. Calrify Question. Create some examples of input and output.

2. Create a boundary, identify the edge cases.

3. Clarify the assumptions

4. Propose the approaches

5. Talk about the solution in mind, most probably brute force.

6. Identify the operations that are taking more time. Try to improvize them.

7. Try to find a better approach to solve the problem

8. Compare the approaches

9. Check with interviewer if you can start coding. This helps you to identify if you were able to identify a better approach.

10. Write the algo steps, as comments

11. create the method definition

12. Write code with simplest example in mind. After simple is working, handle the edge cases.

13. After completing the code, walk through the code line by line, and run agains the sample input and outputs.

14. Explain the space time complexity of the solution.

</details>
<details>
<summary> References
</summary>

# Google Interview preparation

https://www.interviewcake.com/google-interview-questions

https://hackernoon.com/14-patterns-to-ace-any-coding-interview-question-c5bb3357f6ed : common pattern 

https://www.educative.io/courses/grokking-the-coding-interview

https://www.educative.io/courses/coderust-hacking-the-coding-interview

https://hackernoon.com/how-not-to-succeed-in-your-45-minute-coding-interview-2eebd46bd6ec 

http://www.columbia.edu/~jxz2101/ Data structure for interviews

https://practice.geeksforgeeks.org/batch/ppc-1/ : geeks for geeks specially for product based companies



# Practise

https://app.codesignal.com/arcade/intro/level-1

https://leetcode.com/discuss/general-discussion/675445/facebook-interview-experiences-all-combined-from-lc-till-date-07-jun-2020

https://leetcode.com/discuss/general-discussion/677506/top-50-google-tagged-questions-with-links

https://interviewing.io/

https://www.hackerrank.com/

https://www.interviewbit.com/practice/

https://www.topcoder.com/

https://leetcode.com/

https://www.codechef.com/

http://codeforces.com/

https://www.coderbyte.com/

https://www.algoexpert.io/product

https://codesignal.com/

https://www.ideserve.co.in/

https://www.khanacademy.org/computing/computer-science/algorithms

https://www.quora.com/q/dailycodingproblems?ch=3&share=b1a4c8fc&srid=DaXA

https://450dsa.com/


# Video Tutorials
- https://www.coursera.org/specializations/algorithms ( 4 courses series from stanford) (must watch) (to access free : https://www.classcentral.com/report/coursera-signup-for-free/) 
- https://www.coursera.org/learn/algorithms-part1
- https://www.coursera.org/learn/algorithms-part2
- https://www.youtube.com/playlist?list=PLs8TmeZHJEeF2UMA8KCI6g0BMDrVUgB0r : Data Structure and algorithm by Sesh Venugopal

- https://www.edx.org/course/algorithms-design-and-analysis : (stanford)
- https://www.youtube.com/playlist?list=PLXFMmlk03Dt7Q0xr1PIAriY5623cKiH7V
- https://www.youtube.com/playlist?list=PLXFMmlk03Dt5EMI2s2WQBsLsZl7A5HEK6
- http://timroughgarden.org/videos.html

- https://www.youtube.com/channel/UCMNkvKnD3mo3Jj9eTwJllWw (watched)
- https://learning.oreilly.com/videos/from-0-to/9781788626767 (watched)
- https://algs4.cs.princeton.edu/lectures/
- https://cuvids.io/app/video/97/watch/
- https://www.coursera.org/specializations/algorithms
- https://www.coursera.org/learn/algorithms-part1/lecture/RZW72/quick-union-improvements
- https://www.youtube.com/playlist?list=PLDV1Zeh2NRsB6SWUrDFW2RmDotAfPbeHu : Data structures playlist by Google employee
- https://www.youtube.com/playlist?list=PLDV1Zeh2NRsDGO4--qE8yH72HFL1Km93P : Graph playlist by Google employee
- https://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-006-introduction-to-algorithms-fall-2011/lecture-videos/ : MIT Course
- https://www.youtube.com/playlist?list=PLUl4u3cNGP61Oq3tWYp6V_F-5jb5L2iHb : MIT 6006 on youtube


# Youtube channels
https://www.youtube.com/channel/UCMNkvKnD3mo3Jj9eTwJllWw

# TO read
https://blog.scottlogic.com/2010/12/22/sorted_lists_in_java.html : sorted list in java

https://towardsdatascience.com/8-common-data-structures-every-programmer-must-know-171acf6a1a42 

https://discuss.codechef.com/t/data-structures-and-algorithms/6599

https://github.com/jwasham/coding-interview-university

# Blog posts on advice and experiences

## Google interview
https://www.freecodecamp.org/news/why-i-studied-full-time-for-8-months-for-a-google-interview-cc662ce9bb13/

https://lekkas.io/nailing-your-first-google-interview/

http://steve-yegge.blogspot.com/2008/03/get-that-job-at-google.html

https://alexbowe.com/failing-at-google-interviews/

https://www.quora.com/How-should-I-prepare-for-my-Google-interview-if-I-have-1-month-left-and-I%E2%80%99m-applying-for-a-software-engineer-role

https://www.quora.com/How-much-time-did-you-spend-preparing-for-Googles-interviews-Is-everyone-who-got-into-Facebook-Google-etc-really-that-good-to-solve-or-understand-every-classic-algorithm-or-problem


https://www.interviewcake.com/google-interview-questions

https://www.coursera.org/learn/algorithms-part1#syllabus : coursera video tutorial

https://www.coursera.org/learn/cs-tech-interview : Mastering the Software Engineering Interview

https://buildyourfuture.withgoogle.com/ : 

### Amazon & Microsoft

https://www.geeksforgeeks.org/must-do-coding-questions-for-companies-like-amazon-microsoft-adobe/

- https://leetcode.com/discuss/interview-question/376375/

### Videos
https://www.youtube.com/watch?v=XKu_SEDAykw

https://www.youtube.com/watch?v=ko-KkSmp-Lk

# Reference to references

https://github.com/ryanoasis/dev-interview-study-guide

- https://medium.com/better-programming/the-software-engineering-study-guide-bac25b8b61eb : 142 Resources for Mastering Coding Interviews

## TODO

- https://leetcode.com/discuss/general-discussion/460599/blind-75-leetcode-questions

- https://practice.geeksforgeeks.org/courses/must-do-interview-prep?vb=144

- https://www.youtube.com/watch?v=qg0CY00qJqI&list=PLi9RQVmJD2fapKJ4DnZzAn55NJfo5IM1c

- file:///C:/Users/hmnsh/OneDrive/Desktop/CI_DSA_study_guide.pdf

- https://www.youtube.com/playlist?list=PLDV1Zeh2NRsDGO4--qE8yH72HFL1Km93P : Graph Theory Playlist

- https://www.youtube.com/watch?v=tvw4v7FEF1w&list=PLDV1Zeh2NRsB6SWUrDFW2RmDotAfPbeHu&index=5 : Data structures playlist

- https://leetcode.com/contest/biweekly-contest-25/ : leet code biweekly contests

- https://github.com/yoshrawat/leetcode_company_wise_questions : company wise list of questions from leetcode

- https://www.geeksforgeeks.org/must-coding-questions-company-wise/ : company wise list of questions from geeksforgeeks

- https://github.com/jwasham/coding-interview-university

- https://leetcode.com/discuss/interview-experience/904804/salesforce-mts-hyderabad-oct-2020-offer : salesforce
- https://leetcode.com/discuss/interview-experience/546186/salesforce-hackerrank-challenge-hyderabad-21-march-2020-result-awaited : salesforce

</details>


<details>
<summary> General points to solve a problem (in progress)
</summary>

## Identify the Algorithm

- is the data sorted :
	-- If u need to find 1 element in a range
		--- Binary Search
	-- If u need to find a set of elements that fulfill certain constraints
		--- Binary search / Two pointer


- you want to search something
	-- use set
- you want to do operation on no of occurences of words
	- hashMap

- you want to find the min/max
- Find an element closest in value to x in O(log n)
	-- heap
	
- Iterating through the element in sorted order 
	-- tree
	
- When ever we need to process nodes in some order, think of Queue & Stacks
	-- Queue : shortest path, BFS
	
- Range minimum queries in O(1) time
	-- Sparse Table 
	
- If a problem can be broken into smaller sub problem

</details>

## Grokking the Coding Interview questions

https://leetcode.com/discuss/general-discussion/1063128/Grokking-the-Coding-Interview-Questions

# Sliding Window
keywords to identify this pattern : contiguous subarray / continuous subarray

## Type 1
moving of window depends on the size of window.
Implementation : windowStart, windowEnd

[https://leetcode.com/problems/maximum-average-subarray-i/] Maximum Average Subarray I
[https://leetcode.com/problems/minimum-size-subarray-sum/] Minimum Size Subarray Sum [Medium]

Template : Eg Maximum Average Subarray I
```
	public double findMaxAverage(int[] nums, int k) {
        int ws=0;
        int sum=0;
        int maxSum=Integer.MIN_VALUE;
        for(int we=0;we<nums.length;we++){
            sum+=nums[we];
            if(we>=k-1){
                //calculate max
                maxSum=Math.max(maxSum, sum);
                //shrink window
                sum-=nums[ws];
                ws++;
            }
        }
        return (double)maxSum/k;
    }
```

## Type 2
Dynamic moving of window but map not reqd

[https://leetcode.com/problems/max-consecutive-ones-iii/] Max Consecutive Ones III [Medium]


## Type 3
Implementation : ws, we, map(either with freq or last occurence)

[https://leetcode.com/problems/longest-substring-with-at-most-k-distinct-characters] Longest Substring with K Distinct Characters [Subscribe to unlock] -> Similar Problems -> [https://leetcode.com/problems/longest-repeating-character-replacement/] (Type 3) , [https://leetcode.com/problems/max-consecutive-ones-iii/]
[https://leetcode.com/problems/fruit-into-baskets/] Fruit Into Baskets [Medium]
[https://leetcode.com/problems/longest-substring-without-repeating-characters/] Longest Substring Without Repeating Characters [Medium]

## Type 4 
Implementation : ws, we, map(either with freq or last occurence), a counter. If a pattern is provided create a charFreqMap from that pattern.
Iterate the main string and keep on reducing the freq on char match. To reduce the window, we have logic on counter and the main map. 


[https://leetcode.com/problems/permutation-in-string/] Permutation in String [Medium]
[https://leetcode.com/problems/find-all-anagrams-in-a-string/] Find All Anagrams in a String [Medium]
[https://leetcode.com/problems/minimum-window-substring/] Minimum Window Substring [Hard]
[https://leetcode.com/problems/substring-with-concatenation-of-all-words/] Substring with Concatenation of All Words [Hard]



# Two Pointers
keywords to identify : sorted array

[https://leetcode.com/problems/two-sum/] Two Sum [Easy]

[https://leetcode.com/problems/remove-duplicates-from-sorted-array/] Remove Duplicates from Sorted Array [Easy] -> similar [https://leetcode.com/problems/remove-element/] Remove Element [Easy] -> similar [https://leetcode.com/problems/remove-duplicates-from-sorted-array-ii/submissions/] Remove Duplicates from Sorted Array II [Medium]

[https://leetcode.com/problems/squares-of-a-sorted-array/] Squares of a Sorted Array [Easy]
## using binary search
[https://leetcode.com/problems/3sum/] Triplet sum to zero [Medium]
[https://leetcode.com/problems/3sum-closest/] Triplet sum close to target [Medium]
[https://leetcode.com/problems/sort-colors/] Sort colors [Medium]
[https://leetcode.com/problems/4sum/] 4 sum [Medium]

[https://leetcode.com/problems/backspace-string-compare/] Backspace String Compare [Easy]
[https://leetcode.com/problems/shortest-unsorted-continuous-subarray/] Shortest Unsorted Continuous Subarray [Medium]


# Fast & Slow Pointer
[https://leetcode.com/problems/linked-list-cycle/] Linked List Cycle
[https://leetcode.com/problems/middle-of-the-linked-list/] Middle of the Linked List
[https://leetcode.com/problems/happy-number/] happy number
[https://leetcode.com/problems/linked-list-cycle-ii/] In circular linkedlist find the starting node of the cycle
[https://leetcode.com/problems/palindrome-linked-list/] Palindrome Linked List
[https://leetcode.com/problems/reorder-list/] reorder list

# Merge Intervals
[https://leetcode.com/problems/merge-intervals/] Merge Intervals
[https://leetcode.com/problems/insert-interval/] Insert interval
[https://leetcode.com/problems/interval-list-intersections/] Interval List Intersections
[https://leetcode.com/problems/my-calendar-i/] My calendar / conflict assignment
[https://www.lintcode.com/problem/meeting-rooms-ii/] Meeting rooms

# Cyclic Sort
[https://leetcode.com/problems/missing-number/] find missing number
[https://leetcode.com/problems/find-all-numbers-disappeared-in-an-array] find all missing numbers
[https://leetcode.com/problems/find-the-duplicate-number/] Find the duplicate number
[https://leetcode.com/problems/find-all-duplicates-in-an-array/] Find all the duplicate numbers
[https://leetcode.com/problems/first-missing-positive/] Find missing positive number

# In place reversal of linkedlist
[https://leetcode.com/problems/reverse-linked-list/] Reverse a Linkedlist
[https://leetcode.com/problems/reverse-linked-list-ii/] Reverse a sub list
*[https://leetcode.com/problems/reverse-nodes-in-k-group/] Reverse every K-element Sub-list
*[https://leetcode.com/problems/rotate-list/] Rotate the list to the right by k places.

# BFS
[https://leetcode.com/problems/binary-tree-level-order-traversal/] Binary Tree Level Order Traversal [Medium]
[https://leetcode.com/problems/binary-tree-level-order-traversal-ii/] Reverse level order traversal [Medium]
[https://leetcode.com/problems/binary-tree-zigzag-level-order-traversal/] zigzag level order traversal [Medium]
[https://leetcode.com/problems/average-of-levels-in-binary-tree/] Average of Levels in Binary Tree [Easy]
[https://leetcode.com/problems/minimum-depth-of-binary-tree/] Minimum Depth of Binary Tree [Easy]
[https://www.geeksforgeeks.org/level-order-successor-of-a-node-in-binary-tree/] Level Order Successor of a node in Binary Tree
[https://leetcode.com/problems/populating-next-right-pointers-in-each-node/] Populating Next Right Pointers in Each Node
Given a binary tree, connect each node with its level order successor.
[https://leetcode.com/problems/binary-tree-right-side-view/] Binary Tree Right Side View [Medium]



# DFS
[https://leetcode.com/problems/path-sum/] (Binary Tree Path Sum) (easy)
[https://leetcode.com/problems/diameter-of-binary-tree/] (Diameter of Binary Tree) (easy)
[https://leetcode.com/problems/path-sum-ii/] (Paths with sum equal to target) (Medium)
[https://leetcode.com/problems/sum-root-to-leaf-numbers/] (Sum Root to Leaf Numbers) (Medium)
[https://www.geeksforgeeks.org/check-root-leaf-path-given-sequence/] (Path With Given Sequence) (Medium)
[https://leetcode.com/problems/binary-tree-maximum-path-sum/] (Path with Maximum Sum) (hard)


# SubSets
[https://leetcode.com/problems/subsets/] (Distinct Subsets) (Medium)
[https://leetcode.com/problems/subsets-ii/] (Subsets with duplicates)
[https://leetcode.com/problems/permutations/] (Peermutations)
[https://leetcode.com/problems/letter-case-permutation/] String case permutation
[https://leetcode.com/problems/generate-parentheses/] Generate parenthesis

# DP
[https://leetcode.com/problems/maximum-subarray/] (contiguous subarray with maxmum sum) (kaden's algo)