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
* As the standard way of describing a chessboard is to use a letter for a row (also known as a “rank” in chess) and a number for a column (called a “file” in chess)—for example, g2, a3, f1,a8, and so on, a PGN file which contains all the game moves which are described in above format is passed at the command line when running r2_chess_pgn.py.
* pgnparser library is used to parse that block of test
