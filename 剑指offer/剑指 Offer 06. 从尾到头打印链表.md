From https://leetcode-cn.com/problems/cong-wei-dao-tou-da-yin-lian-biao-lcof/

1. [**Recursion**](https://leetcode-cn.com/submissions/detail/199905805/)
```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, x):
#         self.val = x
#         self.next = None

class Solution:
    def reversePrint(self, head: ListNode) -> List[int]:
        if not head:
            return []
        else:
            return self.reversePrint(head.next) + [head.val]
```

Time complexity: O(n)<br/>
Space complexity: O(n)<br/>

2. [**Iteration**](https://leetcode-cn.com/submissions/detail/199906914/)
```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, x):
#         self.val = x
#         self.next = None

class Solution:
    def reversePrint(self, head: ListNode) -> List[int]:
        result = []
        while head:
            result.insert(0, head.val)
            head = head.next
        return result
```

Time complexity: O(n)<br/>
Space complexity: O(n)<br/>

3. [**Stack**](https://leetcode-cn.com/submissions/detail/199907869/)
```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, x):
#         self.val = x
#         self.next = None

class Solution:
    def reversePrint(self, head: ListNode) -> List[int]:
        stack, result = [], []
        while head:
           stack.append(head.val)
           head = head.next
        while stack:
            result.append(stack.pop())
        return result
```

Time complexity: O(n)<br/>
Space complexity: O(n)<br/>
