# Hash Table

### Hash table and hash function
A DS that provides a mapping from keys to values using a technique called hashing.

Used to track item frequency.

### Properties of hash functions
A hash function is a function that maps a key to a whole number in a fixed range.
- If Hx != Hy, x and y are certainly different.
- A hash function must be deterministic.

### Collision resolution methods
1. Separate chaining : maintain a DS to hold all the different values
2. Open addressing : find another place to offset the object
  - Linear probing
  - Quadratic probing
  - Double hash

### Complexity analysis
| Operation | Average | Worst |
| --- | --- | --- |
| Insertion | O(1) | O(n) |
| Removal | O(1) | O(n) |
| Search | O(1) | O(n) |

### Leetcode questions
