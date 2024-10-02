# Redundant-Array

Chef has an array A containing N positive integers. He can perform the following operation on the array as many times as he likes:
Choose integers L and R such that 1 ≤ L ≤ R ≤ N;
Choose a positive integer x;
For every index i from L to R (inclusive of both), set Ai​ = x.
The cost of such an operation is (R − L + 1 )⋅x. Find the minimum cost required to make all the elements of A equal.

from collections import Counter

for _ in range(int(input())):
    n = int(input())

    arr = list(map(int, input().split()))
    d = Counter(arr)

    res = n

    for i in d:
        c = d[i]
        res = min(res, (n - c) * i)

    print(res)
