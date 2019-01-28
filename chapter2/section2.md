# Section 2

## 1. Express the function n^3/1000 - 100n^2 - 100n + 3 in terms of O-notation.

    O(n^3)

## 2. Consider sorting n numbers stored in array A by first finding the smallest element of A and exchanging it with the element in A[1]. Then find the second smallest element of A, and exchange it with A[2]. Continue in this manner for the first n1 elements of A. Write pseudocode for this algorithm, which is known as selection sort. What loop invariant does this algorithm maintain? Why does it need to run for only the first n - 1 elements, rather than for all n elements? Give the best-case and worst-case running times of selection sort in ‚O-notation.

    for i=0 to A.length
        min = -1
        for j=i to A.length
            if min == -1 or A[j] < A[min]: 
                min = j
        
        swap A[i] and A[min]
    
    This algorithm maintains that i > 0 and i < A.length inside the loop and j > i and j < A.length inside the inner loop. It also maintains that at the end of the inner loop, j == A.length and at the end of the outer loop, i == A.length.

    Run time will always be O(N**2) in the best or worst case because it will check the array from i to n(length of array), N times to make sure it has the min element.

## 3.
