
# Lists and Tuples Exercises


1. **Pig Game** (Neller). Implement a game of Pig where the user plays against a "hold at 20 or goal" computer player that rolls until a 1 ("pig") is rolled, or the turn total is greater than or equal to 20, or the score plus the turn total is greater than or equal to 100.  The first player is chosen randomly. **You will most likely want to use a previous exercise as a starting point.**

 - Before the game, randomly select which player the user will be, and print the line "You will be player #.", where # is the user's player number. Then, print an instruction line "Enter nothing to roll; enter anything to hold."
 - Before each turn, print a line with "Player 1 score: " and player 1's score.  Print another line with "Player 2 score: " and player 2's score.  Finally, print a line with "It is player #'s turn.", where "#" is replaced by the current player number.  Play starts with player 1 and then alternates.
 - For each roll, print a line with "Roll: " and the random die roll value (1-6).
 - For each non-"pig" roll 2-6 on the user's turn, prompt the user with "Turn total: ", the turn total, a tab, and "Roll/Hold? ".
 - After a "pig" roll of 1, or a "hold", print a line with "Turn total: " followed by the turn total.  In the case of a "pig", this turn total is 0.  Then, print a line with "New score: " followed by the new score for the current player.


2. **Three-Pile Nim** (Neller). In the 3-pile game of Nim, two players begin with three piles containing one or more objects. In turn, each player chooses a non-empty pile and removes one or more objects from it. (It is legal to take all objects of a pile.) The player taking the last object of the last pile wins.

 In your implementation, you should internally represent the number of objects in each pile as an array of length 3.  Position n in that array will contain the number of objects in pile n.  The program initially reads the 3 initial pile sizes from the user.  Assume that these will be positive integers.  Then the game will begin.

 At the beginning of each turn, the current state of each pile is represented in text as one line per pile, each with the 0-based pile number followed by a colon and a number of asterisks equal to the number of objects currently in the pile.  Then the user inputs two integers: (1) the 0-based  pile number, and (2) the number of objects that are to be removed from that pile.  Assume that such input is a legal play.  Turns continue until all piles are empty. At the end of the game, report who wins.

3. **Chomp**. Chomp is a two-player Nim game, where players alternate taking "bites" out of a rectangular cookie made up of smaller cookie squares. When a player bites a square, they also eat all of the cookie squares that are to the right and below. The player that eats the top left square loses. You can play online [here](https://peterefrancis.com/canvas-games/chomp/).

 In this exercise, you will implement a game of chomp between two human players. First ask the user to input the desired dimensions of the board. Then, alternate asking player 1 and 2 for their move (row & col) until one player eats the top left cookie. Each turn, print the board using asterisks (`*`) for remaining cookie squares and print numbers along the top and right side of the board, showing the row and column numbers. At the end of the game, report the winning player.

4. **More Gettysburg Student Usernames**. In Chapter 3, we created Gettysburg Student usernames, given a first and last name (first four characters of last name + first two characters of first name + #). In this exercise, you will do the same, but this time, create a list of usernames that you have already created. Just as at Gettysburg, when creating a new username, check that the one you are about to create does not already exist. While it does, increment the last two digits.

5. **Nested Tuples**. Ask the user for a non-negative integer. Then print an n-length tuple, where the ith entry contains an i-length tuple with the same property. This can **and should** be done in exactly 5 lines. If your code is longer, try again.

	Sample Transcripts:
	```
	Enter a non-negative integer: 0
	()
	```
	```
	Enter a non-negative integer: 1
	((),)
	```
	```
	Enter a non-negative integer: 2
	((), ((),))
	```
	```
	Enter a non-negative integer: 3
	((), ((),), ((), ((),)))
	```
