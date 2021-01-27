# Static and Dynamic Arrays

### About Arrays

#### Definition
A static array is a fixed length container containing n elements indexable from [0, n-1]

#### When and where to use
Everywhere, such as :
- storing and accessing sequential data
- storing objects
- buffers
- lookup tables
- return multiple values
- cache answers

#### Complexity
| Action      | Static| Dynamic  |
| ----------- |------| -----|
| Access      | O(1) | O(1) |
| Search      | O(n) | O(n) |
| Insertion   | - | O(n) |
| Apppending  | - | O(1) |
| Deletion    | - | O(n) |

#### Static array
- 44,12,-5
- 0,1,2

#### Dynamic array
Can grom and shrink in size
- A.add()
- A.remove()

### Dynamic Array implementation
A way is to use a static array and keep tracking the number of array.

### Code implementation
- [Source code link](https://github.com/williamfiset/data-structures)

### LeetCode Questions
11, 26, 27, 41, 42, 45, 55, 80, 121, 122, 123, 128, 134, 164, 188, 189, 217, 243, 244, 245, 274, 275, 277, 287, 299, 309, 334

Practice records :

| Num | 1 | 2 | 3 |
|-----|---|---|---|
| 11  | N |   |   |
| 26  | Y |   |   |
| 27  | Y |   |   |
| 41  | Y |   |   |
| 42  | N |   |   |
| 45  | N |   |   |
| 55  | N |   |   |
| 80  | Y |   |   |
| 121 | Y |   |   |
| 122 | Y |   |   |
| 123 | N |   |   |
| 128 | N |   |   |
| 134 | N |   |   |
| 164 | ? |   |   |
| 188 | ? |   |   |
| 189 | Y |   |   |
| 217 | Y |   |   |
| 243 | - |   |   |
| 244 | - |   |   |
| 245 | - |   |   |
| 274 | Y |   |   |
| 275 | Y |   |   |
| 277 | - |   |   |
| 287 | Y |   |   |
| 299 | Y |   |   |
| 309 | ? |   |   |
| 334 | N |   |   |
