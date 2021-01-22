
# `for` Loops

Recall that with `while` loops, you are able to loop code until a condition is no longer `True`. This often takes the form:

```python
i = 0
while i < 5:
	# code block to
	# do something
	# with `i`
	i += 1
```

You have a counter `i`, and you are repeating a block of code for each value that `i` takes on before `i == 10` is `True`. Another (and admittedly easier) way to think about this process, is to execute the code block

```python
# code block to
# do something
# with `i`
```

for each value of `i` given as successive elements of the list `[0, 1, 2, 3, 4]`.

Python's `for` loops, do just that! In fact, `for` loops are able to *iterate* over any *iterable* object, such as lists, tuples, and strings. This means that with a `for` loop, you can execute a section of code a predetermined number of times (which corresponds to the length of the iterable) where each time, the value of some variable changes to the next element of the iterable. As you will see, this simplifies many situations where you previously used counters and `while` loops.

## Transition to `range()`

The basic for loop iterates over an iterable and has the following simple syntax:

```python
for var in iterable:
	# do something with `var`
```

In each loop, the variable `var` is assigned to be the next element in `iterable`, and the code block is executed with that value of `var`.

Here is an example: we can express the following `while` loop much more succinctly with a `for` loop:

```python
i = 0
while i < 5:
	print(i)
	i += 1
```
> `0`
>
> `1`
>
> `2`
>
> `3`
>
> `4`


```python
for i in [0, 1, 2, 3, 4]:
	print(i)
```
> `0`
>
> `1`
>
> `2`
>
> `3`
>
> `4`

Actually, python has a built in function to allow an even more efficient version:

```python
for i in range(5):
	print(i)
```
> `0`
>
> `1`
>
> `2`
>
> `3`
>
> `4`

`range()` is a special kind of iterable that computes its elements as they are needed (see the chapter on generators). For now we will skip the specifics of how `range()` works and just learn how to use it. In the last example how we supplied `5` to `range()`, and we got back the non-negative integers less than `5`. Each iteration of the `for` loop gets the next integer from `range()`.

We can call `list()` on `range()` to create a list of the elements returned in order to more efficiently see what we are getting.

In general, `range(a)` will return the positive integers less than `a`.

```python
list(range(10))
```
> `[0, 1, 2, 3, 4, 5, 6, 7, 8, 9]`

`range(a, b)` will return the integers greater than or equal to `a` and less than `b`:

```python
list(range(3, 10))
```
> `[3, 4, 5, 6, 7, 8, 9]`

`range(a, b, c)` will return the integers greater than or equal to `a` and less than `b`, incrementing by the integer `c`:

```python
list(range(3, 10, 2))
```
> `[3, 5, 7, 9]`


`range()` is very useful for when you know the number of loops you want to do, and/or the variable you want to change is an integer or can be indexed in a list/tuple/string/etc.


## More Basic Iteration

Just as lists are iterables that are collections of their elements, strings are iterables that are collections of characters. Therefore, we can use a `for` loop to iterate over characters in a string:

```python
for char in "abcdefg":
	print(char)
```
> `a`
>
> `b`
>
> ...
>
> `f`
>
> `g`


Here is a more interesting example:

```python
build = ""
base = "12tf3687iugytd586r97togfi9r7034rtr8q27u0b3"
for char in base:
	if char.isnumeric():
		build += char
print(build)
```
> `123687586979703482703`

Here we iterate over the characters in the string `base` and concatenate the numeric characters to the string `build`. Finally, we print `build`.

Iterating over lists and tuples have the same syntax.

## Caution with Infinite loops

As stated before, `for` loops are generally used when the number of iterations is known. However, there are still situations that can create infinite loops. Consider the following `for` loop:

```python
a = [1, 2, 3, 4]
for i in a:
	print(i)
	a.append(i)
```

You may expect this code to print only four lines, but since we are adding to the list that is being iterated over, this loop will continue indefinitely. Let's break it down:

 - First `a = [1, 2, 3, 4]`.
 - Then `i = 1`, and `a = [1, 2, 3, 4, 1]`
 - Then `i = 2`, and `a = [1, 2, 3, 4, 1, 2]`
 - Then `i = 3`, and `a = [1, 2, 3, 4, 1, 2, 3]`
 - Then `i = 4`, and `a = [1, 2, 3, 4, 1, 2, 3, 4]`
 - Then `i = 1`, and `a = [1, 2, 3, 4, 1, 2, 3, 4, 1]`
 - ...

As you can see, while there is a next element of `a`, the loop will continue, and since we always add another element to `a`, the loop will never terminate. (This can also happen with a while loop).


## `break`, `continue`, and `else`

Here's a short section for you (because these three keywords work just the same as with `while` loops.

	- `break` is used to exit the loop
	- `continue` is used to move to the next iteration of a loop
	- an `else` block can be put after a `for` loop to run if and only if `break` was not called inside the loop


Here are two (very similar) examples:

```python
for i in range(5):
	if i == 3:
		continue
	if i == 4:
		break
	print(i)
else:
	print("I didn't break")
```
> `0`
>
> `1`
>
> `2`

```python
for i in range(5):
	if i == 3:
		continue
	if i == 6:
		break
	print(i)
else:
	print("I didn't break")
```
> `0`
>
> `1`
>
> `2`
>
> `3`
>
> `4`
>
> `I didn't break`



## `enumerate` and `zip`

`enumerate()` and `zip()` are both functions that return a list of tuples. This is often useful for looping through two or more iterators at once.

`zip()` takes as arguments and number of iterables and returns a `zip` object of tuples, where the nth (zero-based) tuple consists of the nth elements of each of the iterables passed. If the iterables are of different length, the shortest iterable passed will determine the number of tuples returned. We will learn more about how this works internally in a later chapter. For now, we can call `list()` on the zip object return to see what it generates. Here is an example:

```python
list(zip("abcd", [1, 2, 3, 4], ('i', 'ii', 'iii')))
```
> `[('a', 1, 'i'), ('b', 2, 'ii'), ('c', 3, 'iii')]`

As you can see, only three tuples are returned since the third iterable passed to `zip()` only contains three elements.

`enumerate()` is very similar to `zip()`: it takes one iterable object and optionally a starting number (default is 0). Then `enumerate()` returns an `enumerate` iterable object that dispenses tuples, where the nth tuple (zero-based) consists of the nth integer after the starting number, and the nth element of the iterable passed. You can think of `enumerate()` begin a more specific case of `zip()`, since `zip(range(s), iterable)` will serve just the same as `enumerate(iterable, start=s)`.

Here are two examples:

```python
list(enumerate("asdfg"))
```
> `[(0, 'a'), (1, 's'), (2, 'd'), (3, 'f'), (4, 'g')]`

```python
list(enumerate("asdfg", start=3))
```
> `[(3, 'a'), (4, 's'), (5, 'd'), (6, 'f'), (7, 'g')]`


`zip()` and enumerate lend themselves nicely to python `for` loops because (as discussed in a previous chapter). python supports auto-packing and unpacking of tuples and lists, as well as multiple variable assignment. This means that when using a `for` loop to iterate over a `zip` object, you can either take the tuple of arguments as your loop variable, or you can define multiple loop variables at the same time:

```python
for a, b in zip("123", "678"):
	print(f"a={a} b={b}")
```
> `a=1 b=6`
>
> `a=2 b=7`
>
> `a=3 b=8`


```python
for c in zip("123", "678"):
	print(c)
```
> `(1, 6)`
>
> `(2, 7)`
>
> `(3, 8)`


It is remarkable that you can use a starred expression in order to unpack and then repack the contents of a tuple:

```python
for a, *bc in zip("asdf","asdf", "asdf"):
    print(a, bc)
```
> `a ['a', 'a']`
>
> `s ['s', 's']`
>
> `d ['d', 'd']`
>
> `f ['f', 'f']`

In this last example, the starred expression is used to indicate that `bc` should be a list that will comprise of the remaining elements that are unpacked as a comma-separated sequence.


## List Comprehension

Much of the ease of python comes from the capability of doing things in one line that other languages would require multiple statements to complete. You have already seen one-line (ternary) `if`-`else` statements, and in this section, we will take a look at how python uses one-line `for` loops to accomplish this capability.

With *List Comprehension*, you can *safely* populate a list in one line! The notation looks similar to a `for` loop (and reads in English as you would imagine it to behave). Each element of the list is generated one by one. Here is a simple example where we generate a list of ten zeros:

```python
[0 for i in range(10)]
```
> `[0, 0, 0, 0, 0, 0, 0, 0, 0, 0]`

The code to the left of `for` is executed every "loop" to create the next element of the list, while the code to the right determines the loop behavior.

**Note:** It is a common practice to name the loop variable (`i` in this case) just and underscore `_` if the variable is not being used in the loop.

In this example, we create a list of the non-negative perfect squares less than 100:

```python
[i ** 2 for i in range(10)]
```
> `[0, 1, 4, 9, 16, 25, 36, 49, 64, 81]`


As stated before, this method of generating a list is safe because each element of the list is created individually, one at a time. Consider the two following ways to make a list of 5 lists containing 0:

```python
# create the lists
a = [[0]] * 5
b = [[0] for _ in range(5)]

# edit the first element of each list
a[0][0] = 1
b[0][0] = 1

# print the lists
print(a)
print(b)
```
> `[[1], [1], [1], [1], [1]]`
>
> `[[1], [0], [0], [0], [0]]`

You can see how the elements of `a` are all the same object, so all get changed together, while the elements of `b` are independent, so do not all get changed.

List comprehension can be used with an `if` statement to filter items from the list:

```python
[i ** 2 for i in range(10) if i % 2 == 0]
```
> `[0, 4, 16, 36, 64]`

You can also use a one-line `if`-`else` to determine the element that is generated.

```python
[i ** 2 if i % 2 == 0 else i ** 3 for i in range(10)]
```
> `[0, 1, 4, 27, 16, 125, 36, 343, 64, 729]`

Nested `for` loops can also be used in list comprehension:

```python
[(i, j) for j in range(2) for i in range(4)]
```
> `[(0, 0), (1, 0), (2, 0), (3, 0), (0, 1), (1, 1), (2, 1), (3, 1)]`

By examining the order of the tuples in the list above, you can see that the loop to the far right is the "outer" loop and the nesting continues left.

As the last example shows, you can reference the loop variable anywhere to the left of where it was defined. One loop variable can even be used in defining the loop behavior of the next:

```python
[[i + 1 for i in range(j + 1)] for j in range(5)]
```
> `[[1], [1, 2], [1, 2, 3], [1, 2, 3, 4], [1, 2, 3, 4, 5]]`
