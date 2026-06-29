# 2. Add Two Numbers

## Difficulty
Medium

## Problem

You are given two non-empty linked lists representing two non-negative integers.
The digits are stored in reverse order, and each node contains a single digit.
Add the two numbers and return the sum as a linked list.

## Approach

This solution simulates elementary school addition.

1. Create a dummy node to simplify linked list construction.
2. Traverse both linked lists simultaneously.
3. Add the corresponding digits and the carry.
4. Use `divmod()` to calculate:
   - the new carry
   - the digit to store
5. Create a new node with the computed digit.
6. Continue until both lists and the carry are exhausted.

## Algorithm

1. Initialize:
   - `dummy`
   - `current`
   - `carry = 0`
2. While either list has nodes or carry exists:
   - Read current values (`0` if node is missing).
   - Compute total.
   - Calculate carry and digit.
   - Append digit to the result list.
   - Move pointers forward.
3. Return `dummy.next`.

## Complexity Analysis

- **Time Complexity:** O(max(m, n))
- **Space Complexity:** O(max(m, n)) (for the output linked list)

## Python Solution

```python
# Definition for singly-linked list.
# class ListNode(object):
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next

class Solution(object):
    def addTwoNumbers(self, l1, l2):
        dummy = ListNode()
        current = dummy
        carry = 0

        while l1 or l2 or carry:
            v1 = l1.val if l1 else 0
            v2 = l2.val if l2 else 0

            total = v1 + v2 + carry
            carry, digit = divmod(total, 10)

            current.next = ListNode(digit)
            current = current.next

            l1 = l1.next if l1 else None
            l2 = l2.next if l2 else None

        return dummy.next
```
