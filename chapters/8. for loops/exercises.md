
# `for` loop Exercises

1. **Divisors**. Ask the user for a non-negative integer `n` and then print a list of all of the positive divisors of that integer.

	Sample Transcripts:

	```
	Enter an integer: 50
	Positive divisors: [1, 2, 5, 10, 25, 50]
	```
	```
	Enter an integer: -100
	Positive divisors: [1, 2, 4, 5, 10, 20, 25, 50, 100]
	```

2. **Prime Numbers**. Ask the user for an integer `n`, and then print whether `n` is prime.

	Sample Transcripts:
	```
	Enter an integer: 16
	16 is not prime
	```
	```
	Enter an integer: -5
	-5 is prime
	```
	```
	Enter an integer: 0
	0 is not prime
	```


3. **Unique Elements**. Define a list `a`. Then define and print a list with only the unique elements of `a` (e.g. if `a` contains 1 twice, print 1 only once).

4. **Min, Max, Sum, and Product.** Define a list `a` of `float`s (and/or `int`s). Then print the minimum, maximum, sum, and product of `a` without using `min()`, `max()`, or `sum()`.

5. **String Palindromes.** Ask for a string `s`. Then use `zip()` and a for loop to print whether `s` is a palindrome. If `s` is not a palindrome, print the palindrome that has `s` as a base. For example, if `s` is `'race'`, the new palindrome that should be printed is `'racecar'`.

	Sample Transcript:
	```
	Enter a string: race
	'race' not a palindrome but 'racecar' is
	```
	```
	Enter a string: racecar
	'racecar' is a palindrome
	```

6. **Magic Square**. Ask the user for an odd positive integer `n` at least 3, and then print the [Magic Square](https://en.wikipedia.org/wiki/Magic_square) of size `n`.

	Algorithm (from Neller):
	> Assign 1 to our initial current position: the bottom row, middle column. Place each successive value (up to `n ** 2`) in the first of the following positions that is unoccupied:
	>	1. one space down and to the right, or
	>	2. one space up.
	>
	> Positions wrap around the sides, top and bottom.

	Make sure that when printing, you space the numbers so that each column is aligned, is the width of the largest number in the square, and is separated by one space.

	Sample Transcript:

	```
	Enter an odd positive integer at least 3: 5
	11  18  25  2   9  
	10  12  19  21  3  
	4   6   13  20  22
	23  5   7   14  16
	17  24  1   8   15
	```
	```
	Enter an odd positive integer at least 3: 3
	4  9  2
	3  5  7
	8  1  6
	```

7. **Fibbonacci**. Print the first 200 Fibonnacci numbers, starting at 1, 2, 3,.... This can be done in 4 lines (64 characters to be exact) *and should take no more than a second of computation time*.


8. **Tables Tables Tables**. One of the many uses python tends to serve is that of data processing, and string formatting. In this exercise, you will learn how to load data from a csv file and print the markup code necessary to print the data as a table in one of three popular languages.

	Look up the way that either an HTML, a LaTeX, or a MarkDown Table is formatted (pick one). Then, use the `readline()` function (look it up) to open the file "iris.csv" and print either the HTML, LaTeX, or MarkDown code necessary to print the data as a table in one of those languages.

	There are many ways to do this, but one would be to first load in the data and save it in a two dimensional array and then do all of the printing. (As an extra challenge, you can try to print in more than one of the languages and print both "minified" and "beautified" versions of the table code).

	By hand, this would be a tedious task. Hopefully, you see the benefit of using Python.
