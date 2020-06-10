# `while` Loop Exercises

Complete the following exercises in a Jupyter notebook and then push the notebook to the "learning-python" repository in your GitHub account. **Above each exercise, create a markdown cell with an "H3" heading of the number of the exercise.**


> [Pig](http://cs.gettysburg.edu/projects/pig) is a folk jeopardy dice game with simple rules: Two players race to reach 100 points. Each turn, a player repeatedly rolls a die until either a 1 ("pig") is rolled or the player holds and scores the sum of the rolls (i.e. the turn total). At any time during a player's turn, the player is faced with two decisions:
- roll - If the player rolls a
  - (1) the player scores nothing and it becomes the opponent's turn.
  - (2-6) the number is added to the player's turn total and the player's turn continues.
- hold - The turn total is added to the player's score and it becomes the opponent's turn.

These exercises build on each other, so don't be afraid to reuse your code. However, in each exercise, be sure to "factor out common code", so there are no two separate, nearly identical sections of code.


1. **Hold-at-20 Pig Turn** (Neller). Simulate a single turn of Pig where a player rolls until a 1 ("pig") is rolled, or the turn total is greater than or equal to 20.
 - For each roll, print a line with "Roll: " and the random die roll value (1-6).
 - After a "pig" roll of 1, or a "hold", print a line with "Turn total: " followed by the turn total.  In the case of a "pig", this turn total is 0.

If you are unfamiliar with generating random numbers in python, check the Appendix for information on the `random` module.

Sample Transcripts:

Seed 0:
```
Roll: 4
Roll: 4
Roll: 1
Turn total: 0
```

Seed 1:
```
Roll: 2
Roll: 5
Roll: 1
Turn total: 0
```

Seed 2:
```
Roll: 1
Turn total: 0
```

Seed 3:
```
Roll: 2
Roll: 5
Roll: 5
Roll: 2
Roll: 3
Roll: 5
Turn total: 22
```




2. **Hold-at-20-or-Goal Turn** (Neller). Given a player's score, simulate a single turn of Pig where a player rolls until a 1 ("pig") is rolled, or the turn total is greater than or equal to 20, or the score plus the turn total is greater than or equal to 100.

- Initially, prompt the user with "Score? ".
- For each roll, print a line with "Roll: " and the random die roll value (1-6).
- After a "pig" roll of 1, or a "hold", print a line with "Turn total: " followed by the turn total.  In the case of a "pig", this turn total is 0.  Then print a line with "New score: " followed by the new score.


Sample Transcripts:

Seed 0:
```
Score?  60
Roll: 4
Roll: 4
Roll: 1
Turn total: 0
New Score: 60
```

Seed 3:
```
Score?  90
Roll: 2
Roll: 5
Roll: 5
Turn total: 12
New Score: 102
```

Seed 42:
```
Score?  3
Roll: 4
Roll: 3
Roll: 2
Roll: 2
Roll: 4
Roll: 5
Turn total: 20
New Score: 23
```




3. **Hold-at-20-or-Goal Game** (Neller). Simulate a single solitaire game of Pig where a player rolls until a 1 ("pig") is rolled, or the turn total is greater than or equal to 20, or the score plus the turn total is greater than or equal to 100.

- For each roll, print a line with "Roll: " and the random die roll value (1-6).
- After a "pig" roll of 1, or a "hold", print a line with "Turn total: " followed by the turn total.  In the case of a "pig", this turn total is 0.  Then, print a line with "New score: " followed by the new score.


Sample transcripts:

Seed 0:
```
Roll: 4
Roll: 4
Roll: 1
Turn total: 0
New Score: 0
Roll: 3
Roll: 5
Roll: 4
Roll: 4
Roll: 3
Roll: 4
Turn total: 23
New Score: 23
Roll: 3
Roll: 5
Roll: 2
Roll: 5
Roll: 2
Roll: 3
Turn total: 20
New Score: 43
Roll: 2
Roll: 1
Turn total: 0
New Score: 43
Roll: 5
Roll: 3
Roll: 5
Roll: 6
Roll: 5
Turn total: 24
New Score: 67
Roll: 2
Roll: 3
Roll: 1
Turn total: 0
New Score: 67
Roll: 6
Roll: 1
Turn total: 0
New Score: 67
Roll: 6
Roll: 3
Roll: 4
Roll: 5
Roll: 1
Turn total: 0
New Score: 67
Roll: 3
Roll: 4
Roll: 3
Roll: 5
Roll: 6
Turn total: 21
New Score: 88
Roll: 2
Roll: 5
Roll: 4
Roll: 4
Turn total: 15
New Score: 103
```

Seed 1:

```
Roll: 2
Roll: 5
Roll: 1
Turn total: 0
New Score: 0
Roll: 3
Roll: 1
Turn total: 0
New Score: 0
Roll: 4
Roll: 4
Roll: 4
Roll: 6
Roll: 4
Turn total: 22
New Score: 22
Roll: 2
Roll: 1
Turn total: 0
New Score: 22
Roll: 4
Roll: 1
Turn total: 0
New Score: 22
Roll: 4
Roll: 4
Roll: 5
Roll: 1
Turn total: 0
New Score: 22
Roll: 6
Roll: 4
Roll: 3
Roll: 6
Roll: 2
Turn total: 21
New Score: 43
Roll: 5
Roll: 1
Turn total: 0
New Score: 43
Roll: 3
Roll: 1
Turn total: 0
New Score: 43
Roll: 1
Turn total: 0
New Score: 43
Roll: 1
Turn total: 0
New Score: 43
Roll: 6
Roll: 5
Roll: 1
Turn total: 0
New Score: 43
Roll: 4
Roll: 6
Roll: 2
Roll: 4
Roll: 6
Turn total: 22
New Score: 65
Roll: 1
Turn total: 0
New Score: 65
Roll: 5
Roll: 2
Roll: 4
Roll: 4
Roll: 5
Turn total: 20
New Score: 85
Roll: 2
Roll: 3
Roll: 2
Roll: 6
Roll: 2
Turn total: 15
New Score: 100
```


4. **Average Pig Turns** (Neller). What is the expected number of turns per solitaire game with a hold-at-20-or-goal play policy?  Simulate a given number of solitaire Pig games where a player rolls until a 1 ("pig") is rolled, or the turn total is greater than or equal to 20, or the score plus the turn total is greater than or equal to 100.  Report the average number of turns per game. *You'll want to copy Exercise "Hold-at-20-or-Goal Game" as a starting point.*

- Initially, prompt the user with "Games? ". (Larger numbers, will tend to yield better estimations.)
- After the simulations, print "Average turns: " followed by the average turns taken per simulated game. **DO NOT PRINT ALL OF THE GAME DATA (roll, player turns)!**

Sample Transcript:
(seed 0)
```
Games?  1000
Average number of turns: 12.631
```
**Optional Challenge:** Instead of asking for a number of games, ask for an integer `n` and then calculate the average number of turns to the decimal place `10^(-n)`.


5. **Two Player Pig** (Neller). Simulate a single solitaire game of Pig where a player rolls until a 1 ("pig") is rolled, or the turn total is greater than or equal to 20, or the score plus the turn total is greater than or equal to 100. *You'll want to copy Exercise "Hold-at-20-or-Goal Game" as a starting point.*

- Before each turn, print a line with "Player 1 score: " and player 1's score.  Print another line with "Player 2 score: " and player 2's score.  Finally, print a line with "It is player #'s turn.", where "#" is replaced by the current player number.  Play starts with player 1 and then alternates.
- For each roll, print a line with "Roll: " and the random die roll value (1-6).
- After a "pig" roll of 1, or a "hold", print a line with "Turn total: " followed by the turn total.  In the case of a "pig", this turn total is 0.  Then, print a line with "New score: " followed by the new score for the current player.
- At the end of the game, print the winner.

**Hint:** Have a `current_player` variable whose value changes at the end of each turn (this can be done in one line!). Have a variable `score` that you set at the beginning of a turn, depending on the current player.

Sample transcript:
(Seed 0)
```
Player 1 score: 0
Player 2 score: 0
It is Player 1's turn.
Roll: 4
Roll: 4
Roll: 1
Turn total: 0
New Score: 0
Player 1 score: 0
Player 2 score: 0
It is Player 2's turn.
Roll: 3
Roll: 5
Roll: 4
Roll: 4
Roll: 3
Roll: 4
Turn total: 23
New Score: 23
Player 1 score: 0
Player 2 score: 23
It is Player 1's turn.
Roll: 3
Roll: 5
Roll: 2
Roll: 5
Roll: 2
Roll: 3
Turn total: 20
New Score: 20
Player 1 score: 20
Player 2 score: 23
It is Player 2's turn.
Roll: 2
Roll: 1
Turn total: 0
New Score: 23
Player 1 score: 20
Player 2 score: 23
It is Player 1's turn.
Roll: 5
Roll: 3
Roll: 5
Roll: 6
Roll: 5
Turn total: 24
New Score: 44
Player 1 score: 44
Player 2 score: 23
It is Player 2's turn.
Roll: 2
Roll: 3
Roll: 1
Turn total: 0
New Score: 23
Player 1 score: 44
Player 2 score: 23
It is Player 1's turn.
Roll: 6
Roll: 1
Turn total: 0
New Score: 44
Player 1 score: 44
Player 2 score: 23
It is Player 2's turn.
Roll: 6
Roll: 3
Roll: 4
Roll: 5
Roll: 1
Turn total: 0
New Score: 23
Player 1 score: 44
Player 2 score: 23
It is Player 1's turn.
Roll: 3
Roll: 4
Roll: 3
Roll: 5
Roll: 6
Turn total: 21
New Score: 65
Player 1 score: 65
Player 2 score: 23
It is Player 2's turn.
Roll: 2
Roll: 5
Roll: 4
Roll: 4
Roll: 5
Turn total: 20
New Score: 43
Player 1 score: 65
Player 2 score: 43
It is Player 1's turn.
Roll: 3
Roll: 1
Turn total: 0
New Score: 65
Player 1 score: 65
Player 2 score: 43
It is Player 2's turn.
Roll: 5
Roll: 1
Turn total: 0
New Score: 43
Player 1 score: 65
Player 2 score: 43
It is Player 1's turn.
Roll: 1
Turn total: 0
New Score: 65
Player 1 score: 65
Player 2 score: 43
It is Player 2's turn.
Roll: 6
Roll: 4
Roll: 6
Roll: 6
Turn total: 22
New Score: 65
Player 1 score: 65
Player 2 score: 65
It is Player 1's turn.
Roll: 6
Roll: 1
Turn total: 0
New Score: 65
Player 1 score: 65
Player 2 score: 65
It is Player 2's turn.
Roll: 5
Roll: 4
Roll: 3
Roll: 2
Roll: 6
Turn total: 20
New Score: 85
Player 1 score: 65
Player 2 score: 85
It is Player 1's turn.
Roll: 3
Roll: 6
Roll: 1
Turn total: 0
New Score: 65
Player 1 score: 65
Player 2 score: 85
It is Player 2's turn.
Roll: 2
Roll: 5
Roll: 2
Roll: 2
Roll: 2
Roll: 5
Turn total: 18
New Score: 103
Player 2 wins!
```




6. **First-Player Advantage** (Neller). There is an advantage to going first in Pig, but how big an advantage is it for “hold at 20 or goal” play?  We wish to estimate the probability of a first-player win with a hold-at-20-or-goal play policy.  Simulate a given number of two-player Pig games where a player rolls until a 1 ("pig") is rolled, or the turn total is greater than or equal to 20, or the score plus the turn total is greater than or equal to 100.  Report the fraction of games won by the first player. *You'll want to copy Exercise "Two Player Pig" as a starting point.*

- Initially, prompt the user with "Games? ". (Larger numbers, will tend to yield better estimations.)
- After the simulations, print "Probability of first player win: " followed by the fraction of simulated games won by the first player. **DO NOT PRINT ALL OF THE GAME DATA (roll, player turns)!**

Sample Transcript:

```
Games?  10000
Probability of first player win: 0.5332
```

7. **The Euclidean Algorithm**. Use the Euclidean Algorithm to find the gcd of two positive integers:

- Prompt the user for two positive integers, `a` and `b` (you can assume that the input is correct).
- While `b` is not `0`, set `a_prime` to `b` and set `b_prime` to (`a` modulus `b`), where a' and b' are the new values of `a` and `b` for the next iteration.
- The final value of `a` is the gcd of the two integers.

Sample Transcript:
```
Integer a? 504
Integer b? 2226
Greatest common divisor of a and b: 42
```


8. **Making a Do-While Loop**. In some situations, you know that you are always going to want to execute a while loop's body at least once. In some languages other than python, this calls for a "do-while" loop, which evaluates a conditional expression at the **end** instead of the beginning of the loop. This is *not* python syntax, but if python were to have a do-while loop, it would probably look like this:
```
do:
	CODE_BLOCK_TO
	EXECUTE_AT
	LEAST_ONCE
while CONDITION
```

Even though python does not have this native capability, it is possible to recreate the same behavior in python using a **boolean flag**. Do so and recreate the following *fake* python do-while loop:

```
i = int(input("Enter an integer: "))
do:
	print(i)
	i += 1
while i < 3
```

Sample Transcripts:

```
Enter an integer:  -5
-5
-4
-3
-2
-1
0
1
2
```

```
Enter an integer:  4
4
```

```
Enter an integer:  -5
-5
-4
-3
-2
-1
0
1
2
```
