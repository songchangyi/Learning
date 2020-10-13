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
| Apppending  | O(1) | O(1) |
| Deletion    | O(1) | O(n) |

#### Static array
- 44,12,-5
- 0,1,2

#### Dynamic array
Can grom and shrink in size
- A.add()
- Ad.remove()

### Dynamic Array implementation
A way is to use a static array and keep tracking the number of array.

### Code implementation
- [Source code link](https://github.com/williamfiset/data-structures)

### LeetCode Questions
27, 26, 80, 277, 189, 41, 299, 134, 274, 275, 243, 244, 245, 217, 55, 45, 121, 122, 123, 188, 309, 11, 42, 334, 128, 164, 287
