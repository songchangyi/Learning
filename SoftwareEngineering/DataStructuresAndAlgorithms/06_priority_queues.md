# Priority Queues

### A PQ
A queue that each element has a certain priority.

### A Heap
A tree based DS that satisfies the heap invariant.

### When and where
- Dijkstra's Shortest Path algorithm
- fetch the next best / worst
- huffman coding
- BFS
- Minimum Spanning Tree

### Complexity Analysis
| Actions | Complexity |
| --- | --- |
| Binary Heap Construction | O(n) |
| Polling | O(logn) |
| Peeking | O(1) |
| Adding | O(logn) |

| Actions | Complexity |
| --- | --- |
| Naive Removing | O(n) |
| Removing with hash table | O(logn) |
| Naive contains | O(n) |
| Contains with hash table | O(1) |

### Turn Min PQ into Max PQ
Use negative

### Ways of implementing a PQ
Use heaps

### Leetcode questions

| Num | 1 | 2 | 3 |
|-----|---|---|---|
| 215 | N |   |   |
| 347 | Y |   |   |
| 218 | ? |   |   |
| 332 | N |   |   |
| 341 | N |   |   |
