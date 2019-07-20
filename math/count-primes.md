# Count Primes

## Question

Count the number of prime numbers less than a non-negative number, **n**.

**Example:**

```text
Input: 10
Output: 4
Explanation: There are 4 prime numbers less than 10, they are 2, 3, 5, 7.
```

## Method

**Sieve of Eratosthenes** \([https://en.wikipedia.org/wiki/Sieve\_of\_Eratosthenes](https://en.wikipedia.org/wiki/Sieve_of_Eratosthenes)\)

## Complexity 

* Time complexity: O\(n \* sqrt\(n\)\)
* Space complexity: O\(1\)

## Code

**Note:** The question requires **less than** n.

```python
def countPrimes(self, n: int) -> int:
    if n < 3: #number of primes < 3
        return 0
    count, sieve = 0, [True] * n
    for i in range(2, n): #count from 2 since 0 and 1 are not prime
        if sieve[i]:
            count += 1
            for j in range(i*i, n, i):
                sieve[j] = False #remove all multiples
    return count
```

