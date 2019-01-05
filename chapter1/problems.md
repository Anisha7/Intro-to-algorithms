# 1 Comparison of running times

# For each function f(n) and time t in the following table, determine the largest size n of a problem that can be solved in time t, assuming that the algorithm to solve the problem takes f(n) microseconds.

|          |    1     |     1      |  
|          |  second  |   minute   | 
| -------- | -------- | ---------- | 
|  lg*n*   |  10^300k | 2^(36*10^8)| 
| \sqrt{n} |   10^12  | 6 * 10^18  | 
|   *n*    |   10^6   | 3.6 * 10^9 | 
| *n*lg*n* |   62746  | 1.33 * 108 | 
|  *n*^2   |   10^3   | 6.0 * 10^4 | 
|  *n*^3   |   10^2   | 1.5 * 10^3 | 
|  2^*n*   |    19    |     31     | 
|    n!    |    9     |     12     | 

# explainations
First recall that a microsecond is 10^−6 seconds. Hence, 
one second = 10^6 microseconds
one hour = 3600000000 = 3.6 * 10^9 microseconds
one month (assume a month has 30 days) = 2592000000000 = 2.592 * 10^12 microseconds
one century = 3110400000000000 = 3.1104 * 10^15 microseconds.

# for more explainations: https://udel.edu/~caviness/Class/CISC320-02S/exercise-solns/ch01/R-1.7.pdf