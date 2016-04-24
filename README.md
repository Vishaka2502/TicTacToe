Introduction: 


This project is an android based game- ‘Tic Tac Toe’ wherein two users simultaneously play the game on two separate devices connected via bluetooth. The simultaneous game play was made possible by using bluetooth-socket and bluetooth-server-socket.
Tic-tac-toe (also known as Noughts and crosses or Xs and Os) is generally a paper-and-pencil game for two players, X and O, who take turns marking the spaces in a 3×3 grid. The player who succeeds in placing three of their marks in a horizontal, vertical, or diagonal row wins the game.
The following example game is won by the first player, X:


Background:

The board is made up of a 3x3 grid of squares. This means that both the players collectively can fill at most 9 entries.
Traditionally, the first player goes with "X" and the second goes with “0”. Once the game has started the players will not be allowed to change the signs.
These symbols will be placed on the table, in the attempt to have three of them in a row or a column or along a square diagonal.
Players keep alternating moves. The first player to draw three of his or her symbols in a row, whether it is horizontal, vertical, or diagonal, has won tic-tac-toe. 
If all the 9 entries have been filled but still nobody has been able to make a row (either horizontal or vertical or along a square diagonal) then the game ends with a tie.





Functionalities of the Tic Tac Toe game application:
Two players will be able to play the same game simultaneously on different android devices provided they are connected via bluetooth.

1. Client and host establishment: 
	a. One of the user will become a host and the other user will be a client, a
    	    bluetooth-server-socket and a bluetooth-socket will be created for them 
    respectively. 
	b. The client will receive a list of available bluetooth devices through 
    Broadcast-receiver. When he selects the host device to connect, the
    bluetooth-server-socket accepts the request and returns the same
    bluetooth-socket to the host device.

2. Establishing the connection:
	a. After the connection is made, the game screen will be displayed on both the
  	    devices.
b. Initially, host gets gets the first chance with ‘X moves’ and Client gets ‘0
    moves’. 

3. Threads:
a. We have used Threads Initially for the Connection made between the host 
    and the client using Bluetooth-server-socket and Bluetooth-socket.
b. Secondly, We are using receiving threads which listens to the selection
    of Play-Again button. Basically it is continuously listening if “Play-Again” button
    is pressed and that is why even if the control is given to second device, 
    the first device have option to reset the game.
c. Also, we are using receiving threads for receiving move made by the player
    who has the control.

4. Locking protocol: 
	a. To ensure that only one player places his moves at a time, the moves of the
    opposite player have been locked. 
	b. In case a cell already has a move (‘X’ or ‘0’), locking will ensure that no new
    moves are made on the same cell by any user.
c. If any of the user ‘wins’ in the middle of the game, then all the cells in the grid
    will be locked for both the users, so that no new move can be made.



5. Synchronisation: 
a. If any of the user clicks on ‘Play Again’ button, then the game would reset on
    both the devices synchronously. 

6. The turn signifier and the winning message have been displayed in a textview in the
    game screen of each device.    


Concepts of Operating System in ‘Tic Tac Toe’ :
Following are the OS concepts that have been used in the functionality of this project:
Socket
Server Socket
Threads
Locking


Tools Used:
For creating this project, we have used Android Studio software package provided by google.

