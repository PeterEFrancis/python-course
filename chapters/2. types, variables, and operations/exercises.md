# Types, Variables, and Operations Exercises

Complete the following exercises in a Jupyter notebook and then push the notebook to the "learning-python" repository in your GitHub account. **Above each exercise, create a markdown cell with an "H3" heading of the number of the exercise.**


1. Use python to calculate the following:
 - the third power of the sum of 15 more than 25 and 7 less than 30, minus the remainder of 6478 divided by 267
 - the fifth root of 34567 (remember that the nth root of a number is the same as the 1/nth power)
 - the 345678th power of 2 (yes, you can do huge calculations like that now---be excited!)

2. Define a complex variable `a` to any complex value you would like. Then on the next line, do a computation to find the complex modulus of `a`. You may only use the variable `a` in the second line (the code should output the [complex modulus](https://mathworld.wolfram.com/ComplexModulus.html) of whatever `a` is defined to be). **Hint:** Recall that if `a` is the complex number x + yi, the complex modulus of `a` is the square root of x squared plus y squared.

3. Explore the documentation for the `math` module and learn about ten functions and/or variables that you think are useful. Then, demonstrate their use. You can view the documentation here: https://docs.python.org/3/library/math.html.

4. Try to cause some errors (do 5), and make a note of what the errors show you. Then below the bad code, fix it. This will help you in the future when you get these errors accidentally, so you know what caused them and how to fix them. If you are stuck, try things like illegally converting between types or making incomplete statements.

5. What python lines, P and Q, would fill in this truth table in order to demonstrate [DeMorgan's Law](https://en.wikipedia.org/wiki/De_Morgan%27s_laws)? **Hint:** DeMorgan's law states that "not (A or B)" is the same as ... check the link.


|   `x`  |   `y`  | `P`     | `Q`     | `P === Q` |
|:------:|:------:|:-------:|:-------:|:---------:|
| `True` | `True` | `False` | `False` | `True`    |
| `True` | `False`| `False` | `False` | `True`    |
| `False`| `True` | `False` | `False` | `True`    |
| `False`| `False`| `True`  | `True`  | `True`    |


6. Look online for a table that explains python operator precedence and in a few words, explain what operator precedence is. Then program an expression that uses all of the arithmetic operators discussed in "readme.md" and list out the operations in the order that they are executed.

7. Write a program that first sets a variable `f` to some `float` (degree Fahrenheit) and then defines a variable `c` that is the equivalent degree in Celsius. In another cell, do the same thing but in reverse. (Bonus: what degree Fahrenheit and Celsius are the same temperature? This is tedious to figure out now, but will become easy in the near future.)

8. Write a program that calculates the volume and surface area of a cylinder given its height and radius. (Do not approximate pi yourself).

9. Write a program that calculates tip, given the subtotal and gratuity rate. (Remember that there are no fractional pennies!)

10. Given a monthly deposit amount and a yearly interest rate, write a program that finds the value your bank account after 6 months (starting with $0). (This is tedious now but will become easier once you have learned about loops). **Hint:** Suppose you save $100 each month and deposit the money into a savings account with a 3.2% annual interest rate (thus the monthly interest rate is 0.032/12). After the first month the account balance becomes `100 * (1 + (0.032 / 12)) = 100.27`. After the second month, the account balance is `(100 + 100.27) * (1 + (0.032 / 12)) = 200.81`.

11. Write a program that finds the area and perimeter of a regular polygon, given the number of sides and the side length.

12. Write a program that, give two integers, `a` and `b`, displays the quotient and then the remainder of the larger divided by the smaller.

13. `ceil()`, and `floor()` are functions in the `math` module (look them up if you don't know how to use them). Integer *truncation* is just "removing" any decimal part of a number and is done with `int()`. Rounding is done with `round()`.
Write a program that defines a `float` variable `a` and then tests equality of each of these following pairs (done to `a`):
- integer truncation and rounding
- integer truncation and flooring
- integer truncation and ceiling
- rounding and flooring
- rounding and ceiling
- flooring and ceiling

**Bonus:** What is the minimum number of times you have to run the program (different values of `a`) so that you can be sure that each pair of actions on `a` don't always give the same result.
