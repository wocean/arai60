1st 

Linked-list-cycleの問題と返す値が変わっただけで、特に何も変わっていないような・・・

``` python ```
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, x):
#         self.val = x
#         self.next = None

class Solution:
    def detectCycle(self, head: Optional[ListNode]) -> Optional[ListNode]:
        passed_node = set()
        if head is None:
            return None

        current_node = head
        passed_node.add(current_node)

        while current_node.next is not None:
            current_node = current_node.next
            
            if current_node in passed_node:
                return current_node

            passed_node.add(current_node)
        
        return None
``` python ```
