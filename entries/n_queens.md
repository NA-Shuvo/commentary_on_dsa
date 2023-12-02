# N-Queens

The N Queens problem is discussed as one of the prototypical backtracking problems.German chess composer Max Bezzel first composed 8-Queens puzzle for 8 * 8 chess board in 1848. However, the more general version (for N*N chessboard) of this puzzle was proposed by Francois Joseph Eustache Lionnet in 1869. 

## Problem Statement

* Is it possible **to place(or compose) N queens on an N * N chess board so that no two queens are attacking each other?** *An attack occurs when two queens are in the same (i) row, (ii) column or (iii) the same diagonal.*  

* If possible, how many legal compositions are there?  

* For multiple compositions, how many of them are canonical? Note that, there are 92 legal compositions for 8-Queens problelm, but only 12 of them are canonical while others are just rotations or reflections of canonal compositions. Let's define q(N) as the total number of legal compositions.  

* In competitive programming contests N-Queens puzzles are set with other special constraints.


## Solution for 8-Queens puzzle

### Complete Search

#### Filtering Approach

Enumerate all possible combinations and filter for legal composition/s. Number of all posible compositions is <sup>64</sup>C<sub>8</sub>(= 4B approx.) i.e. the number of selection of 8 distinct squares from 64 squares. As each queen can occupy only one column, the number of possible composition further reduses to $8^8 (= 8M approx.)$
        
#### Generative approach

##### Gauss-Laquiere's recursive backtracking algorithm  

Place queens on the board, one row at time, starting with the top row. To place r-th queen on r-th row, methodically try all columns from left to right on that row and if legal place by checking the positions of all queens placed before. Tentatively place a queen in a legal square if found and recursively grope places for queens in later rows. If a legal square found for 8-th queen, count for a legal composition else prune that branch.  
**Complexity:** This algorithm searches legal compositions within $8!$ possible combinations. [All 92 Solution Matrix for 8-Queens puzzle][0]


## Solution for N-Queens puzzle

* For N<15, Gauss-Laquiere's recursive backtracking algorithm is used with faster bit operations.  

* There is no known efficient algorithm that compute q(N) for larger values of N.   
    * The current record is q(27). See [q27 project][1]. 
    * Find values of q(N) for N<27 [here][2].
 

## Programming Problem List
* UVa 167 - The Sultan Successor
* UVa 750 - 8 Queens Chess Problem
* UVa 11085 - 
* UVa 11195 - Another n-Queen Problem

***


[0]: Eight_queen_solution.md
[1]: https://github.com/preusser/q27
[2]: https://www.datagenetics.com/blog/august42012/