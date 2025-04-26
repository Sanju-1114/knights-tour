# Knights Tour

This repository contains a C++ solution for [LeetCode problem 2596: Check Knight Tour Configuration](https://leetcode.com/problems/check-knight-tour-configuration/). The program checks if a given n x n grid represents a valid knight's tour, where a knight visits every square exactly once using standard knight moves.

## Problem Overview

The task is to verify if a 0-indexed n x n grid, with values from 0 to n² - 1, forms a valid knight's tour starting from grid[0][0]. A valid tour requires:
- Starting at grid[0][0] (value 0).
- Moving to each subsequent value (k to k+1) using valid knight moves: (-2, 1), (-1, 2), (1, 2), (2, 1), (2, -1), (1, -2), (-1, -2), (-2, -1).
- Visiting all cells exactly once.

## Solution Details

The solution employs recursive backtracking:
- **Function**: `checkValidGrid(vector<vector<int>> &grid)`
  - Initiates validation from grid[0][0] with expected value 0.
- **Function**: `isValid(vector<vector<int>> &grid, int row, int col, int n, int expVal)`
  - Checks if the current cell has the expected value and if a valid knight move leads to the next value.
  - Base cases:
    - Returns false if the cell is out of bounds or doesn't match `expVal`.
    - Returns true if `expVal` is n² - 1 (last cell).
  - Explores all eight knight moves, returning true if any path is valid.

### Complexity
- **Time Complexity**: O(8^(n²)) in the worst case, as each cell may explore all 8 moves.
- **Space Complexity**: O(n²) for the recursion stack.

## How to Use

1. **Clone the repo**:
   ```bash
   git clone https://github.com/Sanju-1114/knights-tour.git
   cd knights-tour
   ```

2. **Compile and run**:
   ```bash
   g++ knightsTour.cpp -o knightsTour
   ./knightsTour
   ```

3. **Sample Input**:
   ```cpp
   vector<vector<int>> grid = {{0, 3, 6}, {5, 8, 1}, {2, 7, 4}};
   ```
   Outputs `1` (true) or `0` (false) based on tour validity.

## Example

```cpp
Input: grid = [[0,3,6],[5,8,1],[2,7,4]]
Output: false
Explanation: The sequence is invalid as some moves (e.g., 0 to 3) are not valid knight moves.
```

## Contributing

Feel free to submit Pull Requests or open issues for bugs, enhancements, or suggestions.

## License

This project is licensed under the MIT License.

## Contact

Maintained by [Sanju-1114](https://github.com/Sanju-1114). For inquiries, please create an issue in this repository.