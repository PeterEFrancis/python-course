
# Lists and Tuples Exercises


1. **Pig Game** (Neller). Implement a game of Pig where the user plays against a "hold at 20 or goal" computer player that rolls until a 1 ("pig") is rolled, or the turn total is greater than or equal to 20, or the score plus the turn total is greater than or equal to 100.  The first player is chosen randomly. **You will most likely want to use a previous exercise as a starting point.**

	 - Before the game, randomly select which player the user will be, and print the line "You will be player #.", where # is the user's player number. Then, print an instruction line "Enter nothing to roll; enter anything to hold."
	 - Before each turn, print a line with "Player 1 score: " and player 1's score.  Print another line with "Player 2 score: " and player 2's score.  Finally, print a line with "It is player #'s turn.", where "#" is replaced by the current player number.  Play starts with player 1 and then alternates.
	 - For each roll, print a line with "Roll: " and the random die roll value (1-6).
	 - For each non-"pig" roll 2-6 on the user's turn, prompt the user with "Turn total: ", the turn total, a tab, and "Roll/Hold? ".
	 - After a "pig" roll of 1, or a "hold", print a line with "Turn total: " followed by the turn total.  In the case of a "pig", this turn total is 0.  Then, print a line with "New score: " followed by the new score for the current player.

	Sample Transcript:
	(seed 0)
	```
	You will be player 2
	Enter nothing to roll; enter anything to hold.

	Player 1 score: 0
	Player 2 score: 0
	It is player 1's turn
		Roll: 4
		Roll: 1
	Turn total: 0
	New score: 0
	Player 1 score: 0
	Player 2 score: 0
	It is player 2's turn
		Roll: 3
	Turn total: 3
	Roll/Hold?
		Roll: 5
	Turn total: 8
	Roll/Hold?
		Roll: 4
	Turn total: 12
	Roll/Hold?
		Roll: 4
	Turn total: 16
	Roll/Hold?
		Roll: 3
	Turn total: 19
	Roll/Hold? h
	Turn total: 19
	New score: 19
	Player 1 score: 0
	Player 2 score: 19
	It is player 1's turn
		Roll: 4
		Roll: 3
		Roll: 5
		Roll: 2
		Roll: 5
		Roll: 2
	Turn total: 21
	New score: 21
	Player 1 score: 21
	Player 2 score: 19
	It is player 2's turn
		Roll: 3
	Turn total: 3
	Roll/Hold?
		Roll: 2
	Turn total: 5
	Roll/Hold?
		Roll: 1
	Turn total: 0
	New score: 19
	Player 1 score: 21
	Player 2 score: 19
	It is player 1's turn
		Roll: 5
		Roll: 3
		Roll: 5
		Roll: 6
		Roll: 5
	Turn total: 24
	New score: 45
	Player 1 score: 45
	Player 2 score: 19
	It is player 2's turn
		Roll: 2
	Turn total: 2
	Roll/Hold?
		Roll: 3
	Turn total: 5
	Roll/Hold?
		Roll: 1
	Turn total: 0
	New score: 19
	Player 1 score: 45
	Player 2 score: 19
	It is player 1's turn
		Roll: 6
		Roll: 1
	Turn total: 0
	New score: 45
	Player 1 score: 45
	Player 2 score: 19
	It is player 2's turn
		Roll: 6
	Turn total: 6
	Roll/Hold?
		Roll: 3
	Turn total: 9
	Roll/Hold?
		Roll: 4
	Turn total: 13
	Roll/Hold?
		Roll: 5
	Turn total: 18
	Roll/Hold? h
	Turn total: 18
	New score: 37
	Player 1 score: 45
	Player 2 score: 37
	It is player 1's turn
		Roll: 1
	Turn total: 0
	New score: 45
	Player 1 score: 45
	Player 2 score: 37
	It is player 2's turn
		Roll: 3
	Turn total: 3
	Roll/Hold?
		Roll: 4
	Turn total: 7
	Roll/Hold?
		Roll: 3
	Turn total: 10
	Roll/Hold?
		Roll: 5
	Turn total: 15
	Roll/Hold?
		Roll: 6
	Turn total: 21
	Roll/Hold? h
	Turn total: 21
	New score: 58
	Player 1 score: 45
	Player 2 score: 58
	It is player 1's turn
		Roll: 2
		Roll: 5
		Roll: 4
		Roll: 4
		Roll: 5
	Turn total: 20
	New score: 65
	Player 1 score: 65
	Player 2 score: 58
	It is player 2's turn
		Roll: 3
	Turn total: 3
	Roll/Hold?
		Roll: 1
	Turn total: 0
	New score: 58
	Player 1 score: 65
	Player 2 score: 58
	It is player 1's turn
		Roll: 5
		Roll: 1
	Turn total: 0
	New score: 65
	Player 1 score: 65
	Player 2 score: 58
	It is player 2's turn
		Roll: 1
	Turn total: 0
	New score: 58
	Player 1 score: 65
	Player 2 score: 58
	It is player 1's turn
		Roll: 6
		Roll: 4
		Roll: 6
		Roll: 6
	Turn total: 22
	New score: 87
	Player 1 score: 87
	Player 2 score: 58
	It is player 2's turn
		Roll: 6
	Turn total: 6
	Roll/Hold?
		Roll: 1
	Turn total: 0
	New score: 58
	Player 1 score: 87
	Player 2 score: 58
	It is player 1's turn
		Roll: 5
		Roll: 4
		Roll: 3
		Roll: 2
	Turn total: 14
	New score: 101
	The winner is: Player 2
	```

2. **Three-Pile Nim** (Neller). In the 3-pile game of Nim, two players begin with three piles containing one or more objects. In turn, each player chooses a non-empty pile and removes one or more objects from it. (It is legal to take all objects of a pile.) The player taking the last object of the last pile wins.

	 In your implementation, you should internally represent the number of objects in each pile as an array of length 3.  Position n in that array will contain the number of objects in pile n.  The program initially reads the 3 initial pile sizes from the user.  Assume that these will be positive integers.  Then the game will begin.

	 At the beginning of each turn, the current state of each pile is represented in text as one line per pile, each with the 0-based pile number followed by a colon and a number of asterisks equal to the number of objects currently in the pile.  Then the user inputs two integers: (1) the 0-based  pile number, and (2) the number of objects that are to be removed from that pile.  Assume that such input is a legal play.  Turns continue until all piles are empty. At the end of the game, report who wins.

	 **NOTE:** It should not be difficult at all to modify your code to play `k`-pile Nim. In fact, you can write your program generally, so that any number of pile-size inputs can be given.

	Sample Transcript:
	```
	Enter pile sizes: 1 2 3
	0: *
	1: **
	2: ***
	Player 1's turn
	enter pile and number of objects to remove: 2 2
	0: *
	1: **
	2: *
	Player 2's turn
	enter pile and number of objects to remove: 0 1
	0:
	1: **
	2: *
	Player 1's turn
	enter pile and number of objects to remove: 1 2
	0:
	1:
	2: *
	Player 2's turn
	enter pile and number of objects to remove: 2 1
	Player 2 wins!
	```



3. **Chomp**. Chomp is a two-player Nim game, where players alternate taking "bites" out of a rectangular cookie made up of smaller cookie squares. When a player bites a square, they also eat all of the cookie squares that are to the right and below. The player that eats the top left square loses. You can play online [here](https://peterefrancis.com/canvas-games/games/chomp/).

	In this exercise, you will implement a game of chomp between two human players. First ask the user to input the desired dimensions of the board. Then, alternate asking player 1 and 2 for their move (row & col) until one player eats the top left cookie. Each turn, print the board using octothorps (`#`) for remaining cookie squares, and print numbers along the top and left side of the board, showing the row and column numbers. At the end of the game, report the winning player. You may assume that all plays are valid.

	Sample transcript:
	```
	Enter # of rows and cols: 12 12

	 0   1   2   3   4   5   6   7   8   9   10  11
	0   #   #   #   #   #   #   #   #   #   #   #   #  
	1   #   #   #   #   #   #   #   #   #   #   #   #  
	2   #   #   #   #   #   #   #   #   #   #   #   #  
	3   #   #   #   #   #   #   #   #   #   #   #   #  
	4   #   #   #   #   #   #   #   #   #   #   #   #  
	5   #   #   #   #   #   #   #   #   #   #   #   #  
	6   #   #   #   #   #   #   #   #   #   #   #   #  
	7   #   #   #   #   #   #   #   #   #   #   #   #  
	8   #   #   #   #   #   #   #   #   #   #   #   #  
	9   #   #   #   #   #   #   #   #   #   #   #   #  
	10  #   #   #   #   #   #   #   #   #   #   #   #  
	11  #   #   #   #   #   #   #   #   #   #   #   #  

	It is Player 1's turn
	Enter row and column to chomp: 3 3

	 0   1   2   3   4   5   6   7   8   9   10  11
	0   #   #   #   #   #   #   #   #   #   #   #   #  
	1   #   #   #   #   #   #   #   #   #   #   #   #  
	2   #   #   #   #   #   #   #   #   #   #   #   #  
	3   #   #   #  
	4   #   #   #  
	5   #   #   #  
	6   #   #   #  
	7   #   #   #  
	8   #   #   #  
	9   #   #   #  
	10  #   #   #  
	11  #   #   #  

	It is Player 2's turn
	Enter row and column to chomp: 0 1

	 0   1   2   3   4   5   6   7   8   9   10  11
	0   #  
	1   #  
	2   #  
	3   #  
	4   #  
	5   #  
	6   #  
	7   #  
	8   #  
	9   #  
	10  #  
	11  #  

	It is Player 1's turn
	Enter row and column to chomp: 2 0

	 0   1   2   3   4   5   6   7   8   9   10  11
	0   #  
	1   #  
	2  
	3  
	4  
	5  
	6  
	7  
	8  
	9  
	10
	11

	It is Player 2's turn
	Enter row and column to chomp: 0 0
	Player 1 wins!
	```



4. **More Gettysburg Student Usernames**. In Chapter 3, we created Gettysburg Student usernames, given a first and last name (first four characters of last name + first two characters of first name + #). In this exercise, you will do the same, but this time, create a list of usernames that you have already created. Just as at Gettysburg, when creating a new username, check that the one you are about to create does not already exist. While it does, increment the last two digits. Stop input when the user enters nothing. After input is over, print the list of usernames. Note that if the number is 1 digit, there is a leading zero, but if it is more than one digit, there is not leading zero.

	Sample Transcript:
	```
	Enter First and Last Name, separated by a space: peter francis
	username franpe01 added to usernames
	Enter First and Last Name, separated by a space: peter francis
	username franpe02 added to usernames
	Enter First and Last Name, separated by a space: peter francis
	username franpe03 added to usernames
	Enter First and Last Name, separated by a space:
	Usernames: ['franpe01', 'franpe02', 'franpe03']
	```

5. **Nested Tuples**. Ask the user for a non-negative integer. Then print an n-length tuple, where the ith entry contains an i-length tuple with the same property. This can **and should** be done in exactly 5 lines (with only the use of topics we have covered already---no functions, lambdas, or for loops). If your code is longer, try again.

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

6. **Creating copy()**. Write a program that defines a list `a` of integers, and then safely copies `a` into a new array `b`. Do not use `copy()`. The following outline should be tested:

	```python
	a = [1, 2, 3, 4, 5]

	# YOUR CODE HERE TO COPY `a` into `b`

	a[0] = 100
	print(b)
	```
	> `[1, 2, 3, 4, 5]`


7. **Flattening a list of lists**. Define a list of lists of lists ... of lists `a`. Then, create and print a list that contains all of the contents of all of the inner lists of lists ... of lists.

	Outline:

	```python
	a = [1, 2, [3, 4, [5, 6], 7], [8, 9, [10, 11]], 12]

	# YOUR CODE HERE TO CREATE `b`

	print(b)
	```
	> `[1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12]`

8. **Shuffling Arrays**. Define a list of integers `a`. Then
 - write a program to create a new array that has been shuffled by randomly accessing (and removing) the elements from `a`,
 - use the [Fisher Yates Shuffle](https://en.wikipedia.org/wiki/Fisher%E2%80%93Yates_shuffle) to shuffle `a` in-place,
 - use the `random.shuffle()` to shuffle `a` in-place

9. **Reverse a list**. Define a list `a`. Then create a list `b` so that `a[::-1] == b`. (Do this without using `[::-1]`).

	Outline:

	```python
	a = [1, 2, 3, 4, 5, 6, 7, 8]

	# YOUR CODE HERE TO CREATE `b`

	print(b)
	```
	>`[8, 7, 6, 5, 4, 3, 2, 1]`

10. **Pharoh Shuffle**. Define a list `a` (of even length) and then write a program to interlace the first half of `a` with the second half into a new list `b`.
    Outline:

	```python
	a = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

	# YOUR CODE HERE TO CREATE `b`

	print(b)
	```
	>`[1, 6, 2, 7, 3, 8, 4, 9, 5, 10]`
    
    **Challenge:** starting with a list of 52 elements, how many times does this operation need to be done in order to return to the original list?
