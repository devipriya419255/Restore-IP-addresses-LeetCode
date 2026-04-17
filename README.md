# Restore-IP-Addresses-LeetCode

"C implementation of LeetCode #93: Restore IP Addresses using Backtracking. Optimized with string pruning and leading-zero validation."

## 🧩 LeetCode 93: Restore IP Addresses (C Solution)

An algorithmic solution that explores all possible ways to insert dots into a string of digits to form valid IPv4 addresses.

## 📖 Problem Description

A valid IP address consists of exactly four integers separated by single dots. Each integer must be between 0 and 255 (inclusive) and cannot have leading zeros. Given a string `s` containing only digits, return all possible valid IP addresses.

### Example
- **Input:** `s = "101023"`
- **Output:** `["1.0.10.23","1.0.102.3","10.1.0.23","10.10.2.3","101.0.2.3"]`

## 🛠️ Technical Approach

The solution uses **Recursive Backtracking** to partition the string:
- **Constraints Pruning:** If a string is shorter than 4 or longer than 12 characters, it's immediately rejected.
- **Validation Logic:** 
    - Each segment must be between 1 and 3 digits.
    - Segments cannot have leading zeros (e.g., "01" is invalid, but "0" is valid).
    - The numerical value must be $\le 255$.
- **In-place Construction:** Uses a temporary buffer to build the IP string, reducing memory allocation overhead during recursion.

## 📊 Complexity Analysis

- **Time Complexity:** $O(1)$ — Since the number of digits is capped at 12 and each segment is max 3 digits, the total number of combinations is constant and small.
- **Space Complexity:** $O(1)$ — Excluding the output list, the recursion depth is fixed at 4.

## 🚀 How to Run

1. Save the code as `restore_ip.c`.
2. Compile using gcc:
   ```bash
   gcc -O3 restore_ip.c -o restore_ip
