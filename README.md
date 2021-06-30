
### PIKACHU
Finding the best move of a player from a given board state that was played by the opponent player.

#### Search Abstraction:
* Initial State: Given Current board.
* Terminal State: If all pieces of opposite player are killed or the search depth is reached.
* Successors: List of all the valid moves for all the pieces on the board for the current player
* Evaluation function: 3 *(white pikachus - black pikachus) + 1 * (white pichus - black pichus).

#### Overview of Solution:
* We have employed the minimax algorithm with alpha-beta pruning along with iterative deepening search to form the 
  search tree and then back-up up the values upwards that are calculated using the evaluation function applied to the 
  leaf states at that particular depth.

* Our successor function return all possible next moves for a given player (either 'w' or 'b').

* We chose the default alpha and beta values as -100000000 and +10000000 respectively, then Back-up of values upwards 
  using the functions:
	def maxvalue(successor, alpha, beta, depth, player, depthlimit,N):
	def minvalue(successor, alpha, beta, depth, player, depthlimit,N):

* In case our search tree terminal state is encountered when the search tree goes till the complete depth i.e. till the 
  leaf by checking if either the total count of black pieces or white pieces is zero.

* We defined the evaluation function as a sum of weighted features where weight of 3 was given to the difference of 
  white and black Pikachus and weight of 1 to the difference of white and black pichus.

* In the core minimax algorithm, we have used a max heap to get the maximum alpha value for a state.

* At the start we considered the current player as Max player and the opposite player as Min player, then we calculate 
  the max of all the beta which in turn are the minimum of alpha (recurrence). We started with depth 2 for finding the 
  search tree and yield the output and if there is still time remaining from the permissible time limit then we increase 
  the depth by one and search again for better output and yield the new output.

#### Difficulties Faced:
* We faced difficulty in writing the successor function especially during the corner cases when a pichu evolves into a 
  pikachu.

* Another thing where we were confused is the code execution getting stopped after a specific time-limit without reaching 
  the terminal state.In such case after a lot of brain storming we were able to figure out the algorithm by writing an 
  evaluation function that calculates an utility value for all states in that depth and employing iterative deepening 
  method that yields a better next move  for every depth
  
