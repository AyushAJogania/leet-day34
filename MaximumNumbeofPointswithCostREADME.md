# leet-day34

# Maximum Points You Can Obtain from Matrix

This is a problem where you are given a matrix of points and you need to maximize the total points while considering certain constraints. You can pick one cell from each row, and the points you gain from a cell are added to your score. However, if you pick cells that are too far apart horizontally between adjacent rows, you will lose points.

## Problem Statement

You are given a 2D matrix `points` where `points[i][j]` represents the points gained by picking cell `(i, j)` in the matrix. The goal is to find the maximum total points you can obtain while adhering to the constraint that if you pick cell `(r, c1)` in row `r` and cell `(r + 1, c2)` in row `r + 1`, you will subtract `abs(c1 - c2)` from your score.

## Approach

The approach for this problem involves using dynamic programming to keep track of the maximum points you can achieve for each cell. Specifically, we can maintain an array `res` where `res[j]` represents the maximum points you can achieve if you pick the cell `(i, j)` in the current row. We iterate through each row and update the `res` array based on the current row's points and the adjacent cells' effects.

1. Initialize an array `res` of size equal to the number of columns in the matrix, all initialized to zero.

2. Loop through each row in the matrix.
   - For each cell `(i, j)` in the current row:
     - Add the points of cell `(i, j)` to `res[j]`.
     - Update `res[j]` to be the maximum of the current value of `res[j]` and `res[j - 1] - 1` (considering the effect of adjacent cells).

3. After completing the forward pass for each row, do a backward pass for each row (starting from the second last row) to update the `res` array again, considering the effect of adjacent cells.

4. Finally, return the maximum value from the `res` array using `max_element`.

## Complexity Analysis

- Time complexity: O(m * n), where m is the number of rows and n is the number of columns in the matrix.
- Space complexity: O(n), where n is the number of columns in the matrix (used for the `res` array).

## Usage

You can use this solution by initializing a `Solution` object and calling the `maxPoints` function with the given matrix `points`. The function will return the maximum total points you can achieve.

```cpp
class Solution {
public:
    long long maxPoints(vector<vector<int>>& points) {
        // Implement the approach here
    }
};
```

Remember to replace the comment with the actual implementation of the approach mentioned above.

## Example

Here's an example of how you can use the solution:

```cpp
vector<vector<int>> points = {{1, 2, 3}, {1, 5, 1}, {3, 1, 1}};
Solution solver;
long long result = solver.maxPoints(points);
cout << "Maximum total points: " << result << endl;
```

## Conclusion

The problem involves efficiently maximizing the points gained from a matrix while considering the effect of adjacent cell choices. By using dynamic programming to track and update the maximum points achievable for each cell, you can solve this problem effectively.
