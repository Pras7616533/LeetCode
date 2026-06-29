# 1. Two Sum

## Difficulty
Easy

## Problem
Given an array of integers `nums` and an integer `target`, return the indices of the two numbers such that they add up to `target`.

## Approach
This solution uses a hash map (dictionary) to store numbers that have already been visited.

For each number:
1. Calculate the complement (`target - num`).
2. Check if the complement exists in the hash map.
3. If it does, return the indices.
4. Otherwise, store the current number and its index.

## Algorithm
1. Create an empty dictionary `seen`.
2. Iterate through the array using `enumerate()`.
3. Compute the complement.
4. If the complement is found in `seen`, return both indices.
5. Otherwise, store the current number with its index.

## Complexity Analysis
- **Time Complexity:** O(n)
- **Space Complexity:** O(n)
