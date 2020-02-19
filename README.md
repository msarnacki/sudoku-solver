# Sudoku solver

The plan for building this script:
1. [x] first I will define function which checks if putting certain number in certein position is possible
2. I am planning to do it in 2 different ways: 
   1. filling empty cells starting from top left corner and going right and then down
   - [ ] building mechanism which is gonna put first possible value in empty position
   - [ ] if putting no number will be possible in certain place go one place back and try putting next number there and do it untill every position will be correctly filled
   2. checking every empty cell and deciding where to put number first
   - in this case there are two possibilities
     1. there will always be at least one cell where you can put only one number in this cell
         - [ ] put number in all these places and go on with looking for next ones
     2. there won't be cells which you can be sure to put exact number in there
         - [ ] put one of possible numbers in cell and go on
         - [ ] if at some  point there will be an error go back to this cell and put in another possible value
   