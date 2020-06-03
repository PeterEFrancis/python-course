
# Conditionals Exercises

Complete the following exercises in a Jupyter notebook and then push the notebook to the "learning-python" repository in your GitHub account. **Above each exercise, create a markdown cell with an "H3" heading of the number of the exercise.** If there are sample transcripts below an exercise, check your work on each and turn in your assignment with the last example evaluated **EXACTLY AS WRITTEN**.


1. Recreate the behavior of the following `if`-`else` block only using `if` statements. **Hint:** use a boolean flag. A *boolean flag* is a variable that is set to either `True` or `False` during one process in order to be used to determine the behavior of a different process.

```python
if 1 > 2:
  print("1 is greater than 2")
else:
  print("1 is less than or equal to 2")
```


2. **Can I ride?** Ask for a height in feet and inches (use two `input()`s). Then convert the height to only inches. If the number of inches is at least 45 and at most 60, print "you can ride". Otherwise, print "you can't ride". If the inputs are not integers, print "invalid input". You can assume that inputs are numbers.

Sample transcripts:

```
enter a height in feet and inches
feet:  4
inches:  2
you can't ride
```
```
enter a height in feet and inches
feet:  1
inches:  6
you can't ride
```
```
enter a height in feet and inches
feet:  1.3
inches:  2.2
invalid input
```


3. **One line sign evaluator.** Copy the following code and fill in the blanks. The result should print the sign of `a`. It is an example of a nested ternary statement.

```python
a = float(input("enter a number: "))
print(f"a = {a} is " + ("positive" if _____ else "negative" if _____ else "zero"))
```

Sample transcripts:

```
enter a number:  0
a = 0 is zero
```
```
enter a number:  1.6
a = 1.6 is positive
```


4. **Even or odd?** Ask for a positive integer using `input()`. Then print whether it is "odd" or "even". If the input is not a number, print "not a number". If the input is a number but is not an integer, print "not an integer". **Hint:** Use `replace()` and `isnumeric()`.

Sample transcripts:
```
Enter a number:  abc
not a number
```
```
Enter a number:  2.1
not an integer
```
```
Enter a number:  2
even
```


5. **Get that grade!** Ask for a score between 0 and 100. Print the letter grade associated.

| Score     | Grade |
|:---------:|:-----:|
| (90, 100] | A     |
| (80, 90]  | B     |
| (70, 80]  | C     |
| (60, 70]  | D     |
| [0, 60]   | F     |

Sample transcripts:
```
Enter a score:  88.5
B
```
```
Enter a score:  95
A
```


6. **Rock Paper Scissors.** Ask for two plays ("rock", "paper", or "scissors") for Player A and Player B. Then display the winner. Make sure you handle any kind of capitalization on the input.

Sample transcripts:

```
Enter A's play:  rock
Enter B's play:  paper
B wins
```

```
Enter A's play:  Scissors
Enter B's play:  Paper
A wins
```

```
Enter A's play:  paper
Enter B's play:  Paper
draw
```

**Hint:** This can be done with exactly four `if`, two `elif`, and four `else` statements (not in that order). This can also be done with one `if`-`else`-`elif` and 5 of boolean operators.


7. **BMI calculation.** Ask for weight in pounds and a height in inches. Then calculate BMI using the formula:

> BMI = (weight in pounds * 703) / (height in inches) ^ 2

Round the BMI to the nearest 10th. Then display the BMI and the associated rating:

| BMI                         | Rating        |
|:----------------------------|:--------------|
| less than 18.5              | Underweight   |
| 18.5 - 24.9                 | Normal Weight |
| 25 - 29.9                   | Overweight    |
| greater than or equal to 30 | Obese         |


Sample Transcripts:
```
Enter weight in pounds:  140
Enter height in inches:  50
A BMI of 39.4 is Obese
```
```
Enter weight in pounds:  127.7
Enter height in inches:  60
A BMI of 24.9 is Normal Weight
```
```
Enter weight in pounds:  70
Enter height in inches:  55
A BMI of 16.3 is Underweight
```

8. **Is it a leap year?** Ask for a year and determine if it is a leap year. A year is a leap year if it divisible by 4 but not by 100, or if it is divisible by 400. You may assume that an integer is entered.

Sample transcripts:
```
Enter a year:  2020
leap year
```
```
Enter a year:  1962
not a leap year
```
```
Enter a year:  1800
not a leap year
```

9. **Find the day of the week based on the date.** Ask for a date (a month, day of the month, and year). Then display the day of the week, which can be found using the following algorithm. Make sure your program excepts any capitalization.

- First, find the "month code":

| Month                     | Month Code |
|:-------------------------:|:----------:|
| April, July               | 0          |
| January, October          | 1          |
| May                       | 2          |
| August                    | 3          |
| February, March, November | 4          |
| June                      | 5          |
| September, December       | 6          |

- If the month is January or February and the year is a leap year, subtract one from the month code.
- Find the "century offset", which is 2 if the year is less than 1900, -1 if the year is greater than 1999, and 0 otherwise.
- Take the last two digits of the year and divide them by 4, disregarding the remainder.
- Add to this number the last two digits of the year, the "month code", the day of the month, and the century offset.
- The remainder of this sum, when divided by seven, is the "day code".

| Day       | Day Code |
|:---------:|:--------:|
| Saturday  | 0        |
| Sunday    | 1        |
| Monday    | 2        |
| Tuesday   | 3        |
| Wednesday | 4        |
| Thursday  | 5        |
| Friday    | 6        |

Sample transcripts:

```
day:  6
month:  December
year:  1960

The day of the week on December 6, 1960 is Tuesday.
```
```
day:  1
month:  june
year:  2020

The day of the week on June 1, 2020 is Monday.
```
```
day of the month:  30
month:  January
year:  2059

The day of the week on January 30, 2059 is Thursday.
```
```
day of the month:  1
month:  January
year:  1600

The day of the week on January 1, 1600 is Wednesday.
```


10. **Pig "Keep Pace and End Race" Advisor**. (From Neller) Pig is a folk jeopardy dice game with simple rules: Two players race to reach 100 points. Each turn, a player repeatedly rolls a die until either a 1 ("pig") is rolled or the player holds and scores the sum of the rolls (i.e. the turn total). At any time during a player's turn, the player is faced with two decisions:

- **roll** - If the player rolls a
  - 1: the player scores nothing and it becomes the opponent's turn.
  - 2 - 6: the number is added to the player's turn total and the player's turn continues.
- **hold** - The turn total is added to the player's score and it becomes the opponent's turn.

Given a player's score i, the opponent's score j, and the current turn total k, advise a player to "roll" or "hold" according to this "keep pace and end race" policy:

- If the player's score i plus the turn total k is greater than or equal to the goal score of 100, hold.
- Otherwise, if either player has a score greater than or equal to 71, roll.
- Otherwise, roll if and only if the turn total is less than 21 + round((j - i) / 8).

Ask the user for the "Player's score", "Opponent's score", and "Turn total", respectively. Given these inputs, output "roll" or "hold" according to the "keep pace and end race" policy above.

Sample Transcripts:
```
Player's score? 79
Opponent's score? 42
Turn total? 21
hold
```
```
Player's score? 37
Opponent's score? 71
Turn total? 48
roll
```
```
Player's score? 71
Opponent's score? 0
Turn total? 20
roll
```
```
Player's score? 42
Opponent's score? 57
Turn total? 22
roll
```
```
Player's score? 42
Opponent's score? 57
Turn total? 23
hold
```


11. Research how to tell if a file exists: https://www.w3schools.com/python/python_file_remove.asp. Demonstrate this.
