# Types, Variables, and Operations

##  Types

Data in python comes in a variety of *types*:

 - Text Type:	`str`
 - Numeric Types:	`int`, `float`, `complex`
 - Sequence Types:	`list`, `tuple`, `range`
 - Mapping Type:	`dict`
 - Set Types:	`set`, `frozenset`
 - Boolean Type:	`bool`
 - Binary Types:	`bytes`, `bytearray`, `memoryview`

Different data types are useful for different tasks, so it is important to understand how each one works. In this chapter, we will be learning about numberic and Boolean types as well as breifly discussing tuples. In following chapters we will learn about the other data types.

The type of a data object can be found by calling `type()` on it.

```python
type(42)
```
> `<class 'int'>`

Before learning more about types, it will be useful to learn about variables.

## Variables

Variables are used to store data in easily memorable names. One common style used to name variables is "cammel case", where the first letter of each word (except the first word) is capitalized.

The following code uses the `=` assignment operator to set the variable `myFirstVariable` (which is in cammel case) to the integer value `42`.

```python
myFirstVariable = 42
```

Another common style is to separate lowercase words with underscores:

```python
my_second_variable = 43
```

Uppercase variable names with words separated by underscored often refer to constant values:

```python
NUMBER_OF_STUDENTS = 10
```

Although in many cases we will be using single-letter variables to simplify examples, please note that THIS IS NOT GOOD PRACTICE in general. Variable names (like comments) give readers of your code an idea of what is going on!

In python, variables are allowed to be assigned one type, and then later assigned a value of a different type. This is not good practice: ambiguous typing can lead to confusion and errors. (See Appendix for typing in Cython).


## Numeric Types

Numbers in python can be any of 3 types, `int`, `float`, and `complex`.

 - `int` (integer) is a whole number, positive or negative, of any length.
 - `float` ("floating point number") is a number, positive or negative, that can contain a decimal point.
 - `complex` is a complex number of the form `a + bj`, where `a` and `b` are `float`s or `int`s. Note that instead of `i`, `j` or `J` is used to denote the complex unit; the `j` must be direclty adjacent to a `float` or `int` literal.

To create a variable of a certain type, just assign that type to the variable.

```python
x = 1       # int
y = 2.3     # float
z = 4 + 5j  # complex

print(type(x))
print(type(y))
print(type(z))
```
> `<class 'int'>`
>
> `<class 'float'>`
>
> `<class 'complex'>`

You can attain (`float`) powers of ten by using `e`. `1.2e3` is the same as `1.2 * 10 ** 3`:

```python
1.2e3
```
> `1200.0`

You can convert from some types to others by using `int()`, `float()`, and `complex()` methods:

The following table shows which numeric types can convert to others:

| v  can convert to  > | `int` | `float` | `complex` |
|:--------------------:|:-----:|:-------:|:---------:|
|        `int`         |  yes  |   yes   |    yes    |
|       `float`        |  yes  |   yes   |    yes    |
|      `complex`       |  no   |   no    |    yes    |


Simply put, all numeric types can mutually convert, excpet for `complex` data, which cannot convert to `int` or `float`.

Here is an example of converting between numeric types.

```python
x = 1    # int
y = 2.8  # float
z = 1j   # complex


a = float(x)    # convert from int to float
b = int(y)      # convert from float to int
c = complex(x)  # convert from int to complex

print(a)
print(b)
print(c)

print(type(a))
print(type(b))
print(type(c))
```
> `1.0`
>
> `2`
>
> `(1+0j)`
>
> `<class 'float'>`
>
> `<class 'int'>`
>
> `<class 'complex'>`


In most cases, operations between these types are allowed, but the result will always be the "more general" type. For example, an operation on two `int`s will result in an `int`, but adding a float and a complex, for example, will result in a complex. One exception is division (see below).

## Tuples

We will revisit `tuple`s in a later chapter, but this is will serve as a short introduction. Simply, `tuple` objects are ordered collections of other data types and are most useful in moving around small amounts of data. The elements of a tuple can be any other data type.

For example, `(1, 2.2)` is a valid `tuple`.


## Basic Arithmetic Operators
As you begin to learn python, you can think of it as a glorified calculator (a LOT of glorification).

You can use python to perform all of the operations that you have used all your life, and a few more!

Just as you would expect, this bit of code will add 6 and 7:

```python
6+7
```
> 13

Here is a chart summarizing some arithmetic operations in python:

| operator           | name                                      | example input          | output   |
|:------------------:|:-----------------------------------------:|:----------------------:|:--------:|
| `+`                | addition                                  | `5+2`                  | `7`      |
| `-`                | subtraction                               | `5-2`                  | `3`      |
| `*`                | multiplication                            | `5*2`                  | `10`     |
| `/`                | division                                  | `5/2`                  | `2.5`    |
| `%`  	             | modulus (remainder from division)         | `5 % 2`                | `1`      |
| `//`               | Floor division                            | `5 // 2`               | `2`      |
| `divmod(x,y)`      | modular division                          | `divmod(5,2)`          | `(2, 1)` |
| `**` or `pow(x,y)` | exponentiation	                           | `5 ** 2` or `pow(5,2)` | `25`     |
| `abs(x)`           | absolute value                            | `abs(-5)`              | `5`      |
| `complex(re, im)`  | complex construction (im is 0 by default) | `complex(5,2)`         | `5+2j`   |
| `conjugate()`      | complex conjugate                         | `(5+2j).conjugate()`   | `5-2j`   |

(The function `divmod(x,y)` returns the tuple `(x // y, x % y)`).

## More from the `math` Module

Before using functions defined in the `math` module, make sure you import it. You only have to do it once at the top of your code, and here's how:

```python
import math
```
will import everything in the `math` module, but to use it you must use the prefix `math.---`. For example,

```python
import math
math.sin(2)
```
> `0.9092974268256817`

To import specific functions, do this instead:

```python
from math import sin, cos, pi

print(cos(2))
print(pi)
```
> `-0.4161468365471424`
>
> `3.141592653589793`

To import everything you can use the wildcard character `*`:

```python
from math import *
gcd(12,34)
```
> `2`

There are MANY more functions defined in the `math` module (see exercises).


## Boolean Type: `bool`

Very simply, in python there are two possible values for a data object that is of type `bool`: `True` and `False`. In later chapters we will learn to use Boolean values to control the flow of a program.


## Comparison Operators

Comparison operators operate on numbers and return a Boolean value.

This table summarizes:

| operator | name                     | example input | output  |
|:--------:|:------------------------:|:-------------:|:-------:|
|  `==`    | equal                    | `5 == 2`      | `False` |
|  `!=`    | not equal                | `5 != 2`      | `True`  |
|  `>`     | greater than             | `5 > 2`       | `True`  |
|  `<`     | less than                | `5 < 2`       | `False` |
|  `>=`    | greater than or equal to | `5 >= 2`      | `True`  |
|  `<=`    | less than or equal to    | `5 <= 2`      | `False` |


## Logical Operators

Logical operators operate on and return Boolean values.

This table summarizes:

| operator | description                                                 |
|:--------:|:-----------------------------------------------------------:|
|  `and`   | returns `True` if both statements are `True`                |
|  `or`    | returns `True` if one of the statements is `True`           |
|  `not`   | reverse the result, returns `False` if the result is `True` |

This truth table is read along rows and shows how these operations behave.

|   `x`  |   `y`  | `x and y` | `x or y` | `not x` |
|:------:|:------:|:---------:|:--------:|:-------:|
| `True` | `True` |  `True`   | `True`   | `False` |
| `True` | `False`|  `False`  | `True`   | `False` |
| `False`| `True` |  `False`  | `True`   | `True`  |
| `False`| `False`|  `False`  | `False`  | `True`  |


## Bitwise Operators

Binary (base 2) numbers are very import to understand and turn out to be very useful in problem solving. If you are unfamiliar with binary numbers, take a moment to do some research. A good video is https://www.youtube.com/watch?v=b7pOcU1xMks.

Python allows for bitwise operations on integers. These are operations that manipulate the bits themselves. The following table summarizes:

| operator | name        | description                                                                                     |
|:--------:|:-----------:|:-----------------------------------------------------------------------------------------------:|
| `&`      | AND 	       | sets each bit to 1 if both bits are 1                                                           |
| `\|`     | OR	         | sets each bit to 1 if one of two bits is 1                                                      |
| `^`      | XOR	       | sets each bit to 1 if only one of two bits is 1                                                 |
| `~`      | NOT	       | inverts all the bits into 2's compliment form, since the binary number is signed (see exercises)|
| `<<`     | left shift  | shift left by pushing zeroes in from the right                                                   |
| `>>`     | right shift | shift right by pushing zeroes in from the left                                                   |

Recall that the binary representation for 91 is 1011011 and the binary representation of 70 is 1000110.

The following table will help you visualize the operations:

|            |   bit -->| ... | 256 | 128 | 64 | 32 | 16 | 8 | 4 | 2 | 1 |
|:----------:|:--------:|:---:|:---:|:---:|:--:|:--:|:--:|:-:|:-:|:-:|:-:|
| `91`       |          |     |  0  |  0  | 1  | 0  | 1  | 1 | 0 | 1 | 1 |
| `70`       |          |     |  0  |  0  | 1  | 0  | 0  | 0 | 1 | 1 | 0 |
| `91 & 70`  |          |     |  0  |  0  | 1  | 0  | 0  | 0 | 0 | 1 | 0 |
| `91 \| 70` |          |     |  0  |  0  | 1  | 0  | 1  | 1 | 1 | 1 | 1 |
| `91 ^ 70`  |          |     |  0  |  0  | 1  | 0  | 0  | 0 | 0 | 1 | 0 |
| `~91`      |          |     |  0  |  0  | 1  | 0  | 1  | 1 | 1 | 0 | 0 |
| `91 << 2`  |          |     |  1  |  0  | 1  | 1  | 0  | 1 | 1 | 0 | 0 |
| `91 >> 2`  |          |     |  0  |  0  | 0  | 0  | 1  | 0 | 1 | 1 | 0 |


## Assignment Operators

Sometimes, you may wish to be concise about a combined variable assignment and operation. Any of the arithmetic or binary operators can take the place of `op` in the following:

`x op= 3` is the same as `x = x op 3`.

For example,

```python
x = 5
x += 2
```
is the same as

```python
x = 5
x = x + 2
```
