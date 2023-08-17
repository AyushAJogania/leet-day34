# leet-day34

## Problem Statement

Given a binary matrix `mat` where 1 represents land and 0 represents water, you need to find the distance of the nearest 0 for each cell. The distance between two adjacent cells is 1.

## Example

**Input:**
```
mat = [[0,0,0],
       [0,1,0],
       [0,0,0]]
```
**Output:**
```
[[0,0,0],
 [0,1,0],
 [0,0,0]]
```
**Explanation:**
- The cell at (1,1) contains 1, and its nearest 0 is at (1,0) which is at a distance of 1.
- The other cells containing 0 have the nearest 0 at a distance of 0.

## Approach

The approach used in this solution is Breadth-First Search (BFS). We initialize a queue with all the cells containing 0, and then perform BFS to propagate the distances to neighboring cells containing 1.

1. Initialize a result matrix to store the distances.
2. Initialize a queue and push all cells containing 0 into it. Set their distances to 0.
3. Use BFS to process cells from the queue.
4. For each cell processed, calculate the distance to its neighboring cells and push them into the queue if they have not been visited yet.
5. Continue until the queue is empty.
6. Return the resulting matrix containing the distances.

## Complexity Analysis

- Time complexity: O(m * n), where m is the number of rows and n is the number of columns in the matrix.
- Space complexity: O(m * n), as we use a result matrix and a queue to store cells.

## Code Explanation

The code defines a class `Solution` that contains the `updateMatrix` function which implements the above approach.

1. The function takes a binary matrix `mat` as input and returns the resulting matrix containing distances.
2. It initializes the dimensions `m` and `n` of the matrix.
3. It creates a result matrix of the same dimensions, initially filled with -1.
4. It initializes a queue and pushes all cells containing 0 into it. Their distances are set to 0 in the result matrix.
5. It defines the directions to move to neighboring cells.
6. It uses BFS to process cells in the queue. For each cell processed, it calculates distances to its neighbors and pushes them into the queue if needed.
7. Finally, it returns the resulting matrix.

## Conclusion

This solution effectively uses BFS to calculate the distance of each cell to the nearest 0 in a binary matrix. The BFS approach ensures that we process cells in a systematic order and propagate distances correctly.
