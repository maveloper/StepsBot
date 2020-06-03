# StepsBot

## Algorithm:
_This algorithm moves a robot from the upper left corner to the lower right corner of the grid._


### _To get to row r and column c [r, c], we will need to have gone:_

 - Right from [r, c-1] if this is a valid cell - [Path 1]
 - Down from [r-1, c] if this is a valid cell - [Path 2]
 
 
 
### _If we look at [Path 1], to get to [r, c-1], we will need to have gone:_

 - Right from [r, c-2] if this is a valid cell
 - Down from [r-1, c-1] if this is a valid cell
Continue this process until we reach the start cell or until we find that there is no path.

### _Base case:_

 - If the input row or col are < 0, or if [row, col] is not a valid cell
      - Return False
      
      
### _Recursive case:_

We'll memoize the solution to improve performance.

 - Use the memo to see if we've already processed the current cell
 - If any of the following is True, append the current cell to the path and set our result to True:
      - We are at the start cell
      - We get a True result from a recursive call on:
          - [row, col-1]
          - [row-1, col]
 - Update the memo
 - Return the result


### _Complexity:_

 - Time: O(row * col)
 - Space: O(row * col) for the recursion depth
