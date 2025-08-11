テスト
1st( 解けてない。head = [1,1,1] pos = -1 )
どうもなんとなくでループで舐めて書いてしまってカウントしながら正確に揃えることができなくなってしまってる。

```python

# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, x):
#         self.val = x
#         self.next = None

class Solution:
    def hasCycle(self, head: Optional[ListNode]) -> bool:
        checked = set()

        while head is not None and head.next is not None:
            if head.next.val in checked:
                return True
            
            checked.add(head.val)
            head = head.next

        return False


```
