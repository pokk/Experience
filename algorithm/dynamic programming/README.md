# Introduction
---

I always say __Dynamic Programming__ is one of the graceful __Brute-force Algorithm__. The concept is we divide a complex problem to each of smaller simple sub-problems then we pick up a optimal answer from them for obtaining an optimal answer.

Actually, we broken a complex problem to many sub-problems, there're many the same sub-problems we could find. So our solution is to reduce calculating the same sub-problems to only once.
<br>
How can we do it? We could keep the results of sub-problems to the memory. When we need to compute the same problem, just pick it up from the memory. The technique of storing solutions to subproblems instead of recomputing them is called __Memorization__.

# Example: Fibonacci Sequence
---

1. fib(5)
2. fib(4) + fib(3)
3. (fib(3) + fib(2)) + (fib(2) + fib(1))
4. ((fib(2) + fib(1)) + (fib(1) + fib(0))) + ((fib(1) + fib(0)) + fib(1))
5. (((fib(1) + fib(0)) + fib(1)) + (fib(1) + fib(0))) + ((fib(1) + fib(0)) + fib(1))

That's easy to see the sample from __Fibonacci sequence__, there're many _fib(0)_ and _fib(1)_ which we need to calculate serval times. In particular, _fib(2)_ was calculated three times from scratch. In larger examples, many more values of fib, or _subproblems_, are recalculated, leading to an exponential time algorithm.

Now, suppose we have a simple map object, m, which maps each value of fib that has already been calculated to its result, and we modify our function to use it and update it. The resulting function requires only __*O(n)*__ time instead of exponential time (but requires __*O(n)*__ space):

In Python:
```python
map = [0, 1]
def fib(n):
    for num in range(1, n):
        map.append(map(num − 1) + map(num − 2))
    return map[n]
```
