# Largest Sum Contiguous Subarray

## Problem
A given array, no sorting, has negative numbers. Find the sum of contiguous subarray within a one-dimensional array of numbers which has the largest sum.

## Thought
Scanning each number in array, and get the sum with this number and so far sum. If the so far sum is negative, then the next number will be the first number of new subarray, if the so far sum is positive, then track the next number.

## Algorithm
<pre><code>
if now sum > zero:
    now sum = zero

if maximum sum < now sum:
    maximum sum = now sum
</code></pre>

## Steps
[-2, -3, 4, -1, -2, 1, 5, -3]
<br>begin: started number of subarray.
<br>end: ended number of subarray.
<br>now sum: so far sum
<br>maximum sum: the largest sum so far.

- scan -2
    - begin: 1
    - end: 1
    - now sum: -2 smaller than zero, give up this number.
    - maximum sum: 0
- scan -3
    - begin: 2
    - end: 2
    - now sum: -3 small than zero
    - maximum sum: 0
- scan 4
    - begin: 3
    - end: 3
    - now sum: 4 bigger than zero, record it.
    - maximum sum: 4 bigger than before, record it.
- scan -1
    - begin: 3
    - end: 4
    - now sum: 3
    - maximum sum: 4
- scan -2
    - begin: 3
    - end: 5
    - now sum: 1
    - maximum sum: 4
- scan 1
    - begin: 3
    - end: 6
    - now sum: 2
    - maximum sum: 4
- scan 5
    - begin: 3
    - end: 7
    - now sum: 7
    - maximum sum: 7 smaller than now sum, record it.
- scan -3
    - begin: 3
    - end: 7 now sum is smaller than previous step, don't record it.
    - now sum: 4
    - maximum sum: 7
- result
    - begin: 3, end: 7, sub array: [4, -1, -2, 1, 5]
    - maximum sum: 7

## Complexity
Time Complexity: __Big-O(n)__
<br>
Space Complexity: __Big-O(1)__

## Source code
https://github.com/pokk/algorithm/blob/master/weian/DynamicProgramming/largest_sum_contiguous_subarray.py

## Reference
http://www.geeksforgeeks.org/largest-sum-contiguous-subarray/
