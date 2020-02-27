# Sudoku solver

#### Script made fully by myself for training. Solving sudoku is a good example of recursive problems and good opportunity to practise using recursion. I planned to solve this problem in two ways:

### Results (mean from 3 examples from websudoku.com):
- 1st algorithm:
    - Easy: Time = 0,01(3) sec, Recursions = 1433,(6)
    - Medium: Time = 0,224(6) sec, Recursions = 25621,(3)
    - Hard: only 1 from 3 examples ended with succes - other 2 went to over 90 000 recursions and crushed notebook
    - Evil: Time = 0,29 sec, Recursions = 27777,(3)
- 2nd algorithm:
    - Easy: Time = 0,01 sec, Recursions = 13,(6)
    - Medium: Time = 0,14(6) sec, Recursions = 475
    - Hard: Time = 0,751(6) sec, Recursions = 2399,(3)
    - Evil: Time = 0,732(6) sec, Recursions = 2264

## Technologies used:
- Python 3
- Jupyter Notebook
- numpy
- git

### 1st algorithm (DONE): 
1. defining function which checks if putting certain number in certein position is possible
2. it starts from top left cell
3. if the cell is empty (there is 0 in np.array) check if putting there number 1 is possible
    - if it is possible put this number in the cell and go to point 4
    - if it is not possible check next number (up to 9) - when no number can be put in a cell go to point 5
4. go to next empty cell (going right and down) and do point 2
5. go to cell before and check if there is another possible number (point 2) 
    - if there is another possiblity go on with point 3
    - if there is no another possiblity do point 5 again
6. keep doing points 3-5 untill every cell is filled
- [x] it is done but does't work for harder sudoku (for these that need about 100 000 recursions and more - it is very non-optimized)

### 2nd algorithm (DONE):
1. defining function which checks if putting certain number in certein position is possible
2. check every empty cell for how many possiblities of putting number there is in each of them
    - if there are cells where there is only one possibility of putting number, put these numbers in (don't know yet if putting them all at once will be good idea, it shouldn't make any errors if starting point of sudoku won't have errors)
    - if there are no cell where there is only one possibility of putting number, put one of possible numbers in cell which have least possibilities from all empty cells
        - if error will occur (no number will be possible to put in a cell) then go back to last cell where there were more than one possibility, put there another possible number and go on with points 2-3
3. check if every number put in cells in sudoku is valid
4. repeat points 1-2 untill every cell is filled