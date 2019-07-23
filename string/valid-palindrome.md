# Valid Palindrome

## Question

Given a string, determine if it is a palindrome, considering only alphanumeric characters and ignoring cases.

**Note:** For the purpose of this problem, we define empty string as valid palindrome.

**Example 1:**

```text
Input: "A man, a plan, a canal: Panama"
Output: true
```

**Example 2:**

```text
Input: "race a car"
Output: false
```

## Code 

```python
# Python, no Regex build in
def isPalindrome(self, s: str) -> bool:
    l, r = 0, len(s)-1
    while l < r:
        while l < r and not s[l].isalnum():
            l += 1
        while l <r and not s[r].isalnum():
            r -= 1
        if s[l].lower() != s[r].lower():
            return False
        l +=1; r -= 1
    return True
```

```javascript
// Javascript, use Regex filter out all letters
var isPalindrome = function(s) {
    s = s.toLowerCase().replace(/[\W_]/g, '');

    for(let l=0,r=s.length-1; l<=r; ++l,--r){
        if(s[l] != s[r]){
            return false;
        }
    }
    return true;
};
```

