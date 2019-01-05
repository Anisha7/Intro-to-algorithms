# Section 2

# insertion sort = O(c1n**2); good for small inputs
# merge sort = O(c2nlogn); good for large inputs
where c1, c2 are constants that don't depend on n


## 1. Give an example of an application that requires algorithmic content at the application level, and discuss the function of the algorithms involved.

When given multiple dollar bills and coins that need to be sorted, algorithmic content (such as a sorting algorithm) is very much necessary. The algorithm can take the values and sort them in an order. This can then make it easy to even count the number of each value we contain. The algorithm would also save time, as it would do the work much more efficiently, if chosen well.

## 2. Suppose we are comparing implementations of insertion sort and merge sort on the same machine. For inputs of size n, insertion sort runs in 8n^2 steps, while merge sort runs in 64n lg n steps. For which values of n does insertion sort beat merge sort?

Insertion sort has a worst case of O(c1n**2) while merge sort has a worst case of O(c2nlogn). Although this shows that merge sort is faster, insertion sort actually works much faster on small inputs, whereas merge sort is better with large inputs. 
For the above given values, if insertion sort runs in 8n^2 steps and merge sort in 64nlogn steps:
For n = 100: insertion sort takes 8000 steps while merge sort takes 12,800 steps
For n = 10^10: insertion sort takes 8 times 10^20 million steps while merge sort takes 64 times 10^11

As we can see, merge sort is much faster with a large input, but insertion sort beats merge sort on smaller inputs (inputs less than 101). 


## 3. What is the smallest value of n such that an algorithm whose running time is 100n^2 runs faster than an algorithm whose running time is 2^n on the same machine?

**15** is the smallest value where 100n^2 runs faster than 2^n. 

At n = 15, 100n^2 = 22,500 and 2^n = 32,768
At n = 14, 100n^2 = 19,600 and 2^n = 16,384