# Section 1

# 1. Using Figure 2.2 as a model, illustrate the operation of INSERTION-SORT on the array A = < 31, 41, 59, 26, 41, 58>.

State 1: chosen: 41, check if 41 is less than the items preceding it.
A = <31, 41, 59, 26, 41, 58> 
41 is greater than 31, so no swaps are made

State 2: chosen: 59, is 59 less than 41? 31? No swaps are made.
A = <31, 41, 59, 26, 41, 58>

State 3: chosen: 26, is 26 less than 59? 41? 31? Yes, swap. 
A = <26, 31, 41, 59, 41, 58>

State 4: chosen: 41, is 41 less than 59? Yes, swap.
A = <26, 31, 41, 41, 59, 58>

State 5: chosen: 58, is it less than 59? Yes, swap.
A = <26, 31, 41, 41, 58, 59>
Sorted.

# 2. Rewrite the INSERTION-SORT procedure to sort into nonincreasing instead of nondecreasing order.

    for j = 2 to A.length
        key = A[j]
        // Insert A[j]  into the sorted sequence A[1..j-1]
        i = j - 1
        while i > 0 and A[i] < key // nonincreasing; '>' for nondecreasing
            A[i+1] = A[i]
            i = i - 1
        A[i + 1] = key

# 3. Consider the searching problem:
# Input: A sequence of n numbers A= < a1, a2, ..., an > and a value v.
# Output: An index i such that  v= A[i] or the special value NIL if v does not appear in A.

# Write pseudocode for linear search, which scans through the sequence, looking for v. Using a loop invariant, prove that your algorithm is correct. Make sure that your loop invariant fulfills the three necessary properties.

    for i = 0 to A.length
        @assert i >= 0 and i < A.length
        if A[i] == v:
            return i
    @assert i == A.length
    return NIL

# 4. Consider the problem of adding two n-bit binary integers, stored in two n-element arrays A and B. The sum of the two integers should be stored in binary form in an (n+1)-element array C. State the problem formally and write pseudocode for adding the two integers.
    source: https://medium.com/@smellycode/add-two-n-bit-binary-numbers-dafad71bfd09
    function addBinary(a: number[], b: number[]): number[]{
        const c = [];
        let carry = 0;
        let i = 0;
        for (i = 0; i < a.length; i += 1){
            let s = a[i] + b[i] + carry;
            c[i] = s % 2; 
            carry = ~~(s / 2);
        }
        c[i] = carry;
    return c;
    }

    Ex. A = 1011 (11) + B = 0011 (3) [C starts as 00000 (0)]
    1. sum = 1+1+0 = 10 (2), c[1] = 2 % 2 = 0, c[2] = 2/2 = 1
    2. sum = 1+1+1 = 11 (3), c[2] = 3 % 2 = 1, c[3] = 3/2 = 1
    3. sum = 0+0+1 = 01 (1), c[3] = 1 % 2 = 1, c[4] = 1/2 = 0
    4. sum = 1+0+0 = 01 (1), c[4] = 1 % 2 = 1, c[5] = 1/2 = 0
    ^        ^ ^ ^                               ^
    i        A B C, all at position i            note that we store the carry for the NEXT step

    



