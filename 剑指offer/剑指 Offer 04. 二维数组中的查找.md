From: https://leetcode-cn.com/problems/er-wei-shu-zu-zhong-de-cha-zhao-lcof/submissions/

1. [**Binary search**](https://leetcode-cn.com/submissions/detail/199895705/)

Assume there are *n* rows and *m* columns.

```python
class Solution:
    def binarySearch(self, row, target):
        l, r = 0, len(row) - 1
        while l <= r:
            mid = (r - l) // 2 + l
            if row[mid] > target:
                r = mid - 1
            elif row[mid] < target:
                l = mid + 1
            else:
                return True
        return False


    def findNumberIn2DArray(self, matrix: List[List[int]], target: int) -> bool:
        if not matrix or not matrix[0]:
            return False

        for i in range(len(matrix)):
            if self.binarySearch(matrix[i], target):
                return True
        return False
```
Time complexity: O(nlogm)<br/>
Space complexity: O(1)<br/>

2. [**Linear search**](https://leetcode-cn.com/submissions/detail/199890105/)
```python
class Solution:
    def findNumberIn2DArray(self, matrix: List[List[int]], target: int) -> bool:
        if not matrix:
            return False
        r, c = 0, len(matrix[0]) - 1
        while r < len(matrix) and c >= 0:
            if target == matrix[r][c]:
                return True
            elif target > matrix[r][c]:
                r += 1
            elif target < matrix[r][c]:
                c -= 1
        return False
```
Time complexity: O(n + m)<br/>
Space complexity: O(1)<br/>
