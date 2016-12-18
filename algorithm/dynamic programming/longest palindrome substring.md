# Longest Palindromic Substring

## Problem
---
Given a string, find the longest substring which is palindrome. For example, if this given string is "caba", the output should be "aba".

## Thought
---
We can solve this problem with Dynamic Programming.<br>

we check each substring like string[i:j] is palindrome, which substring is in the string, from character i to character j, if the answer is correct, then we can check bigger range like string[i:j+1] or string[i-1:j], even string[i-1:j+1] ... and so on.

## Algorithm
---
This problem we could solve by dynamic programming.
Given a sequence: string[0...n-1], the length of sequence is n.

```python
substring = string[i:j]
if substring[i] == substring[j]:
    dp_table[i+1:j-1] == True:
        dp_table[i:j] = True
```

## Steps
---
string = "caba"
max_length = 0 # the longest length of substring.
start = 0 # substring, start position in string.
<br>

this is dynamic programming table, we initial it.

|       |   c   |   a   |   b   |   a   |
|:-----:|:-----:|:-----:|:-----:|:-----:|
| **c** | false | false | false | false |
| **a** | false | false | false | false |
| **b** | false | false | false | false |
| **a** | false | false | false | false |

### step 1. length = 1, substring is palindrome.
|       |                 c                 |                 a                 |                 b                 |                 a                 |
|:-----:|:---------------------------------:|:---------------------------------:|:---------------------------------:|:---------------------------------:|
| **c** | **<font color="red">true</font>** |               false               |               false               |               false               |
| **a** |               false               | **<font color="red">true</font>** |               false               |               false               |
| **b** |               false               |               false               | **<font color="red">true</font>** |               false               |
| **a** |               false               |               false               |               false               | **<font color="red">true</font>** |

### step 2. length = 2
#### step 2-1. scan ca
Because **c** does not equal **a**, so it's not palindrome.

|       |   c   |                 a                  |   b   |   a   |
|:-----:|:-----:|:----------------------------------:|:-----:|:-----:|
| **c** | true  | **<font color="red">false</font>** | false | false |
| **a** | false |                true                | false | false |
| **a** | false |               false                | false | true  |

#### step 2-2. scan ab

**a** and **b** are different.

|       |   c   |   a   |                 b                  |   a   |
|:-----:|:-----:|:-----:|:----------------------------------:|:-----:|
| **c** | true  | false |               false                | false |
| **a** | false | true  | **<font color="red">false</font>** | false |
| **b** | false | false |                true                | false |
| **a** | false | false |               false                | true  |

#### step 2-3. scan ba
**b ≠ a**

|       |   c   |   a   |   b   |                 a                  |
|:-----:|:-----:|:-----:|:-----:|:----------------------------------:|
| **c** | true  | false | false |               false                |
| **a** | false | true  | false |               false                |
| **b** | false | false | true  | **<font color="red">false</font>** |
| **a** | false | false | false |                true                |

### step 3. length = 3
#### step 3-1. scan cab
**c ≠ b**

|       |   c   |   a   |                 b                  |   a   |
|:-----:|:-----:|:-----:|:----------------------------------:|:-----:|
| **c** | true  | false | **<font color="red">false</font>** | false |
| **a** | false | true  |               false                | false |
| **b** | false | false |                true                | false |
| **a** | false | false |               false                | true  |

#### step 3-2. scan aba

**a = a**, it's palindrome !!!
<br>max_length = 3
<br>start = 1

|       |   c   |   a   |   b   |                 a                 |
|:-----:|:-----:|:-----:|:-----:|:---------------------------------:|
| **c** | true  | false | false |               false               |
| **a** | false | true  | false | **<font color="red">true</font>** |
| **b** | false | false | true  |               false               |
| **a** | false | false | false |               true                |

### step 4. length = 4

**c ≠ a**

|       |   a   |   c   |   a   |                 b                  |
|:-----:|:-----:|:-----:|:-----:|:----------------------------------:|
| **c** | true  | false | false | **<font color="red">false</font>** |
| **a** | false | true  | false |                true                |
| **b** | false | false | true  |               false                |
| **a** | false | false | false |                true                |

### output

substring = string[start:start + max_length] = **"aba"**


## Reference
---
[Geeks](http://www.geeksforgeeks.org/longest-palindrome-substring-set-1/)
<br>
[Weian Github](https://github.com/pokk/algorithm/blob/master/weian/DynamicProgramming/longest_palindrome_substring.py)
