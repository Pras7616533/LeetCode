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
- **Space Complexity:** O(max(m, n))
