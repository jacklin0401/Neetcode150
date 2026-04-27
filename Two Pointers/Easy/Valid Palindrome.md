'''
## LEVEL: EASY
## Problem:
Given a string `s`, return `true` if it is a **plindrome**, otherwise retunr `false`.

A **palindrome** is a string that reads the same forward and backward. It is also case-insensitive and ignores all non-alphanumeric characters.

**Note:** Alphanumeric characters consist of letters `(A-Z, a-z)` and number `(0-9)`. 

**Example 1:**

Input: s = "Was it a car or a cat I saw?"

Output: true

Explanation: After considering only alphanumerical characters we have "wasitacaroracatisaw", which is a palindrome.


**Example 1:**
```
Input: s = "tab a cat"

Output: false
```

Explanation: "tabacat" is not a palindrome.

**Constraints:**

```

    - 1 <= s.length <= 1000
    - s is made up of only printable ASCII characters.
```

## Solution:

First the question mention it is case-insensitive meaning that an A and a are treated the same when comparing we need to use the function `.lower()` or `.upper()` to make them the same when comparing, and also it only want **alphanumeric** character outside of `(A-Z, a-z)` will be ignore. Python having a function `.isalnum()` check if it is a **alphanumeric** and will return false if isn't


```python

class Solution:
    def isPalindrome(self, s: str) -> bool:
        newStr=""

        for i in s:
            if i.isalnum():
                newStr += i.lower()
        return newStr == newStr[::-1]

```