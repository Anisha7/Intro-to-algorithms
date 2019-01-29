# Section 3

## 1. Using Figure 2.4 as a model, illustrate the operation of merge sort on the array A: <3, 41, 52, 26, 38, 57, 9, 49>.

[3] [41] [52] [26] [38] [57] [9] [49]
 [3, 41]  [26, 52]  [38, 57]  [9, 49]
[3, 26, 41, 52]      [9, 38, 49, 57]
      [3, 9, 26, 38, 41, 52, 57]

## 2. Rewrite the MERGE procedure so that it does not use sentinels, instead stopping once either array L or R has had all its elements copied back to A and then copying the remainder of the other array back into A.

MERGE-SORT(A, p, r)
    if p < r:
        q = (p + r)/2
        MERGE-SORT(A, p, q)
        MERGE-SORT(A, q, r)
        MERGE(A, p, q, r)

MERGE(A, p, q, r)
    temp = []
    while (p != q or q != r)
        if (A[p] <= A[q]):
            temp.append(A[p])
            p += 1
        else:
            temp.append(A[q])
            q += 1
    temp += A[p:q]
    temp += A[q:r]
    A = temp

## 3. Use mathematical induction to show that when n is an exact power of 2, the solution of the recurrence
##T(n) =  [ 2                 if n = 2,            ]
##        [ 2T(n/2) + n       if n = 2^k, for k > 1]
##    
##    is T(n) = nlogn.

At each step, the length of the recursive step is halved until the problem size is 1, leading to T(n/2) -> T(n/4) -> ... -> T(1). 
Adding the cost of each level of the tree gets us:
    Top level:      cn
    Second level:   c(n/2) + c(n/2) = cn
    ith level:      (2^i)(cn/2^i) = cn
For a total cost of cn
The total number of levels is logn + 1 where n is the input size

There are logn + 1 levels, each with a cost of cn, thus leading to a total cost of 
    cn(logn + 1) = cnlogn + cn 
    Ignoring the lower order term and constants, the big-O is going to be O(nlogn).

## 4. We can express insertion sort as a recursive procedure as follows. In order to sort A[1..n], we recursively sort A[1..n-1] and then insert A[n] into the sorted array A[1..n-1]. Write a recurrence for the running time of this recursive version of insertion sort.

O(N**2)

## 5. Referring back to the searching problem (see Exercise 2.1-3), observe that if the sequence A is sorted, we can check the midpoint of the sequence against v and eliminate half of the sequence from further consideration. The binary search algorithm repeats this procedure, halving the size of the remaining portion of the sequence each time. Write pseudocode, either iterative or recursive, for binary search. Argue that the worst-case running time of binary search is O(log n).

At each step, the recursive call is half the size of the original. At each step, we check one element. The cost at each level is O(1), and each time the size is split in half until we reach 1.
    Top level: n/2
    Second level: n/4
    Third level: n/8
    ...
    ---> logn
    This is the same as a height of logn

A total cost then is 1*logn, since each step costs 1 and there are logn steps. Thus, the running time of binary search is O(logn)

## 6. Observe that the while loop of lines 5–7 of the INSERTION-SORT procedure in Section 2.1 uses a linear search to scan (backward) through the sorted subarray A[1..j-1]. Can we use a binary search (see Exercise 2.3-5) instead to improve the overall worst-case running time of insertion sort to O(nlogn)?

If the subarray is sorted, then yes we can use binary search to improve the overall worst-case running time.

## 7. Describe a O(nlogn)-time algorithm that, given a set S of n integers and another integer x, determines whether or not there exist two elements in S whose sum is exactly x.

Sort the algorithm using merge sort
Conduct a binary search, adding up the first element and the midpoint and comparing it with x. If it is greater, reduce the scope (midpoint). If it is smaller, increase the scope. Move to the next element if not found. 



