From: https://leetcode-cn.com/problems/xuan-zhuan-shu-zu-de-zui-xiao-shu-zi-lcof/

1. [**Binary search (1)**](https://leetcode-cn.com/submissions/detail/199828322/)
```python
class Solution:
    def minArray(self, numbers: List[int]) -> int:
        if not numbers:
            return 0
        l, r = 0, len(numbers) - 1
        while l < r:
            mid = (r - l) // 2 + l
            if numbers[l] < numbers[r]:
                return numbers[l]
            elif numbers[mid] > numbers[l]:
                l = mid + 1
            elif numbers[mid] < numbers[r]:
                r = mid
            else:
                l += 1
        return numbers[l]
```

2. [**Binary search (2)**](https://leetcode-cn.com/submissions/detail/199831695/)
```python
class Solution:
    def minArray(self, numbers: List[int]) -> int:
        if not numbers:
            return 0
        l, r = 0, len(numbers) - 1
        while l < r:
            mid = (r - l) // 2 + l
            if numbers[l] < numbers[r]:
                return numbers[l]
            elif numbers[mid] > numbers[r]:
                l = mid + 1
            elif numbers[mid] < numbers[l]:
                r = mid
            else:
                l += 1
        return numbers[l]
```

Average time complexity: O(logn)<br/>
Worst time complexity: O(n)<br/>
Space complexity: O(1)<br/>
