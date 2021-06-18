# Chapter 02

## Exercises

### 2.1-2

Rewrite the INSERTION-SORT procedure to sort into nonincreasing instead of nondecreasing order.

A[1..n]

```
INSERTION-SORT(A)

for j = 2 to A.length
    key = A[j]
    i = j - 1
    while i > 0 and A[i] < key
        A[i + 1] = A[i]
        i = i - 1
    A[i + 1] = key
```

### 2.1-3

Linear Search
*****Input**: A[1..n] and a value *v*
**Output**: An index i such that v = A[i] or NIL if *v* dose not exist in A

```
LINEAR-SEARCH(A, v)
    ret = NIL
    for i = 1 to A.length
        if A[i] = v
            ret = i
            break
    return ret
```

Loop Invariant:

* Initialization

  At the beginning ret is NIL
  
* Maintenance

  Before each iteration, ret is always NIL

* Termination

  1. When A[i] is equal to v, we found such an index and assign it to ret; or
  2. When i reach A.length + 1 as we increase i by 1 each loop iteration

  The loop terminate with ret being NIL or exactly the index we need.

### 2.1-4

Binary Addition
**Input**: A[1..n] and B[1..n] consisting of 0 or 1
**Output**: C[1..n+1] conforming that C[1] * 2^0 + C[2] * 2^1 + ... + C[n] * 2^(n-1) + C[n+1] * 2^n = 
                                      A[1] * 2^0 + A[2] * 2^1 + ... + A[n] * 2^(n-1) +
                                      B[1] * 2^0 + B[2] * 2^1 + ... + B[n] * 2^(n-1)

```
BINARY-ADDITION(A, B)
    carry = 0
    for i = 1 to A.length
        sum = A[i] + B[i] + carry
        if sum > 1
            carry = 1
            sum = sum - 2
        C[i] = sum
    C[i] = carry
    return C
```
