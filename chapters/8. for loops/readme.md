
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
for i in a;:
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


## List Comprehension

coming soon

<!-- `"".join()` -->


## `enumerate` and `zip`

coming soon


<!--
readline()

enumerate -->
