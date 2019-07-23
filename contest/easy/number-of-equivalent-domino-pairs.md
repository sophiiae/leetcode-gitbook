# Number of Equivalent Domino Pairs

Given a list of `dominoes`, `dominoes[i] = [a, b]` is _equivalent_ to `dominoes[j] = [c, d]` if and only if either \(`a==c` and `b==d`\), or \(`a==d` and `b==c`\) - that is, one domino can be rotated to be equal to another domino.

Return the number of pairs `(i, j)` for which `0 <= i < j < dominoes.length`, and `dominoes[i]` is equivalent to `dominoes[j]`.

**Example 1:**

```text
Input: dominoes = [[1,2],[2,1],[3,4],[5,6]]
Output: 1
```

**Constraints:**

* `1 <= dominoes.length <= 40000`
* `1 <= dominoes[i][j] <= 9`

```python
def numEquivDominoPairs(self, dominoes: List[List[int]]) -> int:
        mp = {}
        count = 0
        for i in range(0, len(dominoes)):
            add = dominoes[i][0] + dominoes[i][1]
            sub = abs(dominoes[i][0] - dominoes[i][1])
            s = str(add) + "," + str(sub)
            if (s in mp):
                count = count + 1 + mp[s]
                mp[s] += 1
            else:
                mp[s] = 0
        return count
```

