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

2nd

そもそもnode自体の比較をしないといけないのにvalの比較をしていたのが間違い・・・。
Optionalの意味を把握できておらずNoneチェックができていなかったので追加

```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, x):
#         self.val = x
#         self.next = None

class Solution:
    def hasCycle(self, head: Optional[ListNode]) -> bool:
        passed_nodes = set()

        if head is None:
            return False

        current_node = head
        passed_nodes.add(current_node)
            
        while current_node.next is not None:
            current_node = current_node.next 
            if current_node in passed_nodes:
                return True

            passed_nodes.add(current_node) 

        return False
```python
