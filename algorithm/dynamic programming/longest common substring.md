# Longest Common Substring

## Problem
---
Given two strings <font color="gray">__'ACBAD'__</font> and <font color="gray">__'ABAC'__</font> for the input. Your mission is finding a longest common string from this two strings.<br/>
As this input example, you can find a longest common string is <font color="gray">__'ABA'__</font> from them so the answer will be 3.

## Thought
---
We have a thinking is using __*brute-force attack*__ to solve it.
<br/>
1. Show all of the X's substring.
2. Show all of the Y's substring.
3. Pick up the same all substring and chose the longest substring from them.

We can try to calculate the time complexity of them.
<br/>
_Step 1_ Big-O(2^len(X)).
<br/>
_Step 2_ Big-O(2^len(Y)).
<br/>
_Step 3_ We don't need to calculate it because it will be exponential time.
<br/>
This is totally not a good way to solve it.

<br/>
The other way, we try to use __*dynamic programming*__.
<br/>
We can start considering a optimal substructure. Here are two strings X:_GOOD_, Y:_GOTO_, and Z is LCS(X, Y). We can find the same word from the tail of both of strings, we can know there are three conditions will be happened.
1. if __Xt = Yt__ then __Zt <- the tail of the same word__.
2. if __Xt != Yt__ then __Zt <- __.

## Solution
---

## Implementation
---

## Algorithm
---
#### Recursion Form

You can see the form as below:
<br/>
![LCS formula](../../img/LCS formula.png)

## Complexity
---
Time Complexity: __Big-O(mn)__
<br/>
Space Complexity: __Big-O(mn)__

## Source
---
```python
```
