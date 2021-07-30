From: https://leetcode-cn.com/problems/ti-huan-kong-ge-lcof/comments/

Before reading this answer, please say "Python yyds!!!"

1. [**Replace (String method)**](https://leetcode-cn.com/submissions/detail/199903837/)
```python
class Solution:
  def replaceSpace(self, s: str) -> str:
    return s.replace(" ", "%20")
```

2. [**Split and join (String method)**](https://leetcode-cn.com/submissions/detail/199903837/)
```python
class Solution:
    def replaceSpace(self, s: str) -> str:
        return "%20".join(s.split(" "))
```

3. [**Extra string**](https://leetcode-cn.com/submissions/detail/199904555/)
```python
class Solution:
    def replaceSpace(self, s: str) -> str:
        result = ""
        for i in range(len(s)):
            if s[i] == " ":
                result += "%20"
            else:
                result += s[i]
        return result
```
