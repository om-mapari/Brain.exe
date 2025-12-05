AM

Subset

Combination for given \[1,2,3\]
\[\]
\[1\]
\[2\]
\[3\]
\[1,2\]
\[1,3\]
\[2,3\]
\[1,2,3\]

Time complexity 2^N

there are N numbers and 2 decision ( whether to include or leave a number )
\[1,2,3\]
\[1(include/leave), 2(include/leave), 3(include/leave)\]
2\*2\*2 = 2^3
so 2^N

Permutation

Permutation for given \[1,2,3\]
\[1,2,3\]
\[1,3,2\]
\[2,1,3\]
\[2,3,1\]
\[3,1,2\]
\[3,2,1\]
Time complexity N!

for example given N = 5
intially \_ \_ \_ \_ \_
first dash - any one of the 5 numbers so, 5 chances
second dash - any of the 4 remaining numbers so, 4 chances
( one number already chosen for first dash )
...
so 5x4x3x2x1 = 120 ( 5! )

Combination

Combination for given \[1,2,3,4\], k = 2 fixed
\[2,4\]
\[3,4\]
\[2,3\]
\[1,2\]
\[1,3\]
\[1,4\]

Time complexity = nC2 = N!​ / (N−k)! k!

explaination:
for example given N = 4, k = 2
given 2 spots and 4 numbers
\_ \_
first dash - any one of the 4 numbers so, 4 chances
second dash - any of the 3remaining numbers so, 3chances
( one number already chosen for first dash )

4\*3 = 12 = (4\*3\*2\*1)/(2\*1) = N!/(N-K)!
but there are repetitions in this way (1,2) and (2,1) are counted.
(Eliminate repetitions of k numbers)
so to eliminate repetitions we need to find out the number of ways in which k can be arranged
for eg k = 2
\_ \_ ( 2\*1 = 2! ) which is nothing but permuation of K = K!
To Eliminate this ( N!/(N-K)! ) / K!
N!​ / (N−k)! k!

