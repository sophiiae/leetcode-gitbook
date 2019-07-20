# Length of Last Word
## Question 
Given a string s consists of upper / lower-case alphabets and empty space characters `' '`, return the length of last word in the string.

If the last word does not exist, return 0.

**Note:** A word is defined as a character sequence consists of non-space characters only.

**Example:**
```text
Input: "Hello World"
Output: 5
```

## Solution
```python
def lengthOfLastWord(self, s: str) -> int:
    #strip() removes leading and trailing character, default: whitespace
    s = s.strip().split(" ")
    return len(s[-1])
```


