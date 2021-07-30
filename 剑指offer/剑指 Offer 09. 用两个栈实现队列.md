From: https://leetcode-cn.com/problems/yong-liang-ge-zhan-shi-xian-dui-lie-lcof/

1. [**Solution 1 (less effective)**](https://leetcode-cn.com/submissions/detail/199975986/)
```python
class CQueue:

    def __init__(self):
        self.stack1 = []
        self.stack2 = []

    def appendTail(self, value: int) -> None:
        self.stack1.append(value)

    def deleteHead(self) -> int:
        if not self.stack1:
            return -1
        while self.stack1:
            val = self.stack1.pop()
            if self.stack1:
                self.stack2.append(val)
        while self.stack2:
            self.stack1.append(self.stack2.pop())
        return val


# Your CQueue object will be instantiated and called as such:
# obj = CQueue()
# obj.appendTail(value)
# param_2 = obj.deleteHead()
```

2. [**Solution 2 (more effective)**](https://leetcode-cn.com/submissions/detail/199990201/)
```python
class CQueue:

    def __init__(self):
        self.stack1 = []
        self.stack2 = []

    def appendTail(self, value: int) -> None:
        self.stack1.append(value)

    def deleteHead(self) -> int:
        if not self.stack2:
            if not self.stack1:
                return -1
            while self.stack1:
                self.stack2.append(self.stack1.pop())
        return self.stack2.pop()


# Your CQueue object will be instantiated and called as such:
# obj = CQueue()
# obj.appendTail(value)
# param_2 = obj.deleteHead()
```

Space complexity: O(n)<br/>
Worst time complexity: O(n)<br/>
Best time complexity: O(1)<br/>
Avg time complexity: O(1)<br/>
