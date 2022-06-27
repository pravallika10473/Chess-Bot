# Chess-Bot
The Robonaut2  plays the chess  according to the loaded PGN file which contains the all the moves of the game
![chessbot](https://user-images.githubusercontent.com/68220390/175960990-46d741c1-d6d4-40f7-9883-a2be83c1071b.png)
# Implementation
# Robonaut2(R2) Packages
*  https://bitbucket.org/nasa_ros_pkg/nasa_r2_simulator.git
*   https://bitbucket.org/nasa_ros_pkg/nasa_r2_common.git
# Modelling Chess Board and Chess Piece
* roslaunch r2_gazebo r2_gazebo.launch launches R2 into gazebo empty simulation
* To make the modelling simple , all the chess pieces are modeled as identical rectangle blocks in models/chess_piece.sdf.
* Chess Board is modeled in models/chess_board.sdf
* In order to spawn and place these models in a running simulation spawn_chessboard.py script is used, which uses gazebo ros services like deleting and spawning model services.
* Initially spawn_chessboard.py keeps all the rectangular chess pieces in 0,1,6,7 rows on chess board.
# Moving R2 around a chessboard using a PGN file 
* As the standard way of describing a chessboard is to use a letter for a row (also known as a “rank” in chess) and a number for a column (called a “file” in chess)—for example, g2, a3, f1,a8, and so on, a PGN file(chess.pgn) which contains all the game moves which are described in above format is passed at the command line when running r2_chess_pgn.py.
* pgnparser library is used to parse that block of text.
* This task can be implemented by moving to that particular square on the chess board;as the palm is above the chess piece we need to be able to open and close the fingers, to do that MoveIt is used . We have only two states pre-pinch and pinch(open and closed hand positions),these two tasks are hardcoded.
* so as the pgn.loads() function reads the game description into a python list of well defined move strings, we then parse these strings in playGame() to create simple scripted motions to pick up pieces and move them to their landing places.
