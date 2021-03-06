# Lists and Tuples

Tuples and lists are two different data types that contain *other* data types within them and maintain an ordering of those values. They are similar in many ways, but have one big difference.
**lists can be changed while tuples cannot**: tuples (like strings) are *immutable*.


## Tuples

To make a tuple, use parentheses and commas:

```python
my_tuple = (1,'2', 3.4)
```
The code above assigns the tuple containing the int `1`, the string `'2'`, and the float `3.4` to the variable `my_tuple`. As you can see, it is possible to have different data types within a tuple.

If you want to create a tuple with only one element, you must remember to **put a comma after the element**.

```python
# this creates a tuple...
a = (1,)

# ...while this is just a number
b = (1)
```

Like strings, tuples offer item access using zero-based indexing. (Negative indexing and slicing is also allowed). You can also check a tuple's length with `len()`.

```python
new_tuple = ('a', 'b', 'c', 'd', 'e')

third_item = new_tuple[2]
print(third_item)

last_item = new_tuple[-1]
print(last_item)

middle_few = new_tuple[1:3]
print(middle_few)

print(len(new_tuple))
```
> `c`
>
> `e`
>
> `('b', 'c')`
>
> `5`


The only two built-in tuple methods are `count()` and `index()` which return the number of instances, or first the index of, a specified element, respectively. For instance,

```python
tup = ('a', 'a', 'b', 'a', 'c', 'b')

print(tup.count('a'))

print(tup.index('b'))
```
> `3`
>
> `2`


## Lists

To make a list, use square brackets and commas:

```python
my_list = [1,'2', 3.4]
```
Similarly to tuples, it is possible to have different data types within a list. Unlike tuples, a one-element list does not need a comma.

```python
a = [1]
```

Lists also have item access using zero-based indexing, where negative indexing and slicing are allowed, and you can also check a list's length with `len()`.

Since a list can be changed (i.e. it is *mutable*), we have a large new set of possibilities with the list data structure over the tuple data structure.

First of all, list indexing supports item assignment.

```python
new_list = ['a', 'b', 'c', 'd', 'e']

new_list[1] = 'f'

print(new_list)
```
> `['a', 'f', 'c', 'd', 'e']`

The code above changes the first element of `new_list` to be `'f'`. It is possible to change slices of lists as well:

```python
a = [1, 2, 3, 4, 5]

a[1:4] = [6, 6, 6]

print(a)
```
> `[1, 6, 6, 6, 5]`


We can get and remove the last element of a list with the list method `pop()`

```python
a = [1, 2, 3, 4, 5]

last = a.pop()

print(a)
print(last)
```
> `[1, 2, 3, 4]`
>
> `5`

As you can see, `pop()` actually changes the list `a`. Another way to remove something from a list is to use `remove()` and specify the element to remove.

```python
a = [1, 2, 3, 4, 5]

a.remove(2)

print(a)
```
> `[1, 3, 4, 5]`

Yet anther way is to use the keyword `del`, which removes the object specified from memory, this removing it from your list.

```python
a = [1, 2, 3, 4, 5]

del a[1]

print(a)
```
> `[1, 3, 4, 5]`

Be careful, because `del a` will delete (not just empty) the entire list `a`. To empty a list, use `clear()`:

```python
a = [1, 2, 3, 4, 5]

a.clear()

print(a)
```
> `[]`

To add something to a list use `append()`

```python
a = [1, 2, 3, 4, 5]

a.append(6)

print(a)
```
> `[1, 2, 3, 4, 5, 6]`

The argument of `append()` gets added as the last element of `a`. To add multiple elements, use `extend()` and pass as an argument a list.


```python
a = [1, 2, 3, 4, 5]

a.extend([6, 7, 8])

print(a)
```
> `[1, 2, 3, 4, 5, 6, 7, 8]`

We can be specific as to where an element is being added with `insert()`, specifying the index and the element to insert:

```python
a = [1, 2, 3, 4, 5]

a.insert(1, 100)

print(a)
```
> `[1, 100, 2, 3, 4, 5]`

The code above inserts the int 100 into index 1, shifting everything after it to the right.

Evidently, lists have more built in methods than tuples. Here are two more nice ones that change the order of the elements in the list:

`sort()` sorts the elements in a list, optionally taking as an argument a boolean `True` or `False`, specifying that the order should be descending or ascending (default), respectively. Another argument `key` can be specified to determine the sorting behavior, but we will come back to this in the chapter on functions.

```python
a = [1,3,5,4,2]

a.sort()

print(a)
```
> `[1, 2, 3, 4, 5]`


`reverse()` reverses the order of a list:

```python
a = [1, 2, 3, 4, 5]

a.reverse()

print(a)
```
> `[5, 4, 3, 2, 1]`




## More In Common

In this section, we will see more example of ways that lists and tuples are the same.

You can also construct a `tuple` or a list from any object that is *iterable*. We will discuss this more in the chapter on for loops, but you can think of *iterable* objects for now as objects that contain clearly defined "sub-objects". One example of this is a string, which contains characters as its sub-object. To construct a tuple or list of characters from a string, use the conversion functions `tuple()` or `list()`:

```python
string_tuple = tuple('hello')
print(string_tuple)

string_list = list('hello')
print(string_list)
```
> `('h', 'e', 'l', 'l', 'o')`
>
> `['h', 'e', 'l', 'l', 'o']`


You can check containment with the keyword `in`, just like characters in a string:

```python
1 in [1,2,3]
```
> `True`

The same works with a tuple, and returns a boolean `True` or `False`.

Now we can discuss two string methods that involve lists and tuples! The string method `join()` will join the elements of the list or tuple (actually, any iterable can be passed to `join()`) that is passed, with the string that `join()` is called on. For example

```python
"-".join(['a', 'b', 'c'])
```
> `'a-b-c'`

returns a string made from the contents of the list/tuple passed to join, separated by `-`. Note that the elements of the list/tuple passed to join must be strings.

The string method `split()` acts as a kind of the inverse to `join()`, and returns a list of substrings of the string that `split()` is called on that were separated by the string passed to join. For example,

```python
'a-b-c'.split('-')
```
> `['a', 'b', 'c']`


## Tales of Caution

Similarly to strings, there are some operations that can be done on lists and tuples:

```python
a = [1, 2, 3]
b = [4, 5, 6]

print(a + b)

print(a * 3)
```
> `[1, 2, 3, 4, 5, 6]`
>
> `[1, 2, 3, 1, 2, 3, 1, 2, 3]`

The `+` operator returns a new list/tuple that is the concatenation of of the two provided, and `*` returns a new list/tuple that is made of a given number of copies of the list/tuple provided.

Here is the cautionary tale:

```python
# define a list of lists
a = [[0,0,0]] * 3

# now `a` is a 3x3 array of zeros:
# [[0, 0, 0],
#  [0, 0, 0],
#  [0, 0, 0]]

print(a)

# access the second element of the first row and set it to 2
a[0][1] = 2

# you would expect `a` now to be
# [[0, 2, 0],
#  [0, 0, 0],
#  [0, 0, 0]]

# but look...
print(a)
```
> `[[0, 0, 0], [0, 0, 0], [0, 0, 0]]`
>
> `[[0, 2, 0], [0, 2, 0], [0, 2, 0]]`

Why did this change the second value of every row? This happened because when you use the `*` operator, it puts the objects of the outer array (which are other arrays) into the outer array, multiple times. The way this is done is not a "deep" copy, which means that the array that is in index 0 of `a` is the same array object that is in the other indices of `a` as well. Since they are all the same object, changing one will change the others.

Another way to see this is just with item assignment. First consider integers:

```python
# set `a`
a = 1
# assign the value of `a` to `b`
b = a
# change `a`
a += 1
# print b
print(b)
```
> `1`

This is as expected, and the comments probably say what you thought was going on "behind the scenes", but here is a more accurate outline:

```python
# point the variable `a` to the immutable int object 1
a = 1
# point the variable `b` to the same object that `a` points to
b = a
# this is the same as a = a + 1, and since 1 is immutable,
# 1 + 1 returns a different int object, 2; a points to 2 (away from 1)
a += 1
# print the object that b points to
print(b)
```
> `1`

The value of `b` does not change when `a` is changed, but the same behind-the-scenes actions have a different effect on lists, since, unlike integers, lists are **mutable**.

```python
# point the variable `a` to the mutable list object [1,1,1]
a = [1, 1, 1]
# point the variable `b` to the same object that `a` points to
b = a
# change the object that `a` points to
a[0] = 2
# print the object that `b` points to (the same object that `a` points to)
print(b)
```
> `[2, 1, 1]`

So why did `b` change when we changed `a`? Since `a` and `b` point to the same object, changing one will change the other. To reiterate, with **immutable** types (like tuples or numeric types, for example), this is not the case: if `a` points to 2 and `b` points to what `a` points to, there is no way to change the "2 object", so if the value of `a` changes, it must be because it was pointed to something else.

If you want to copy a list into another variable (make a new object) then you can use the `copy()` list method. Here is the same example, but with `copy()` to create a new list object, instead of pointing to the old one.

```python
# point the variable `a` to the mutable list object [1,1,1]
a = [1, 1, 1]
# point the variable `b` to a copy of the same object that `a` points to (an entirely different object)
b = a.copy()
# change the object that `a` points to
a[0] = 2
# print the object that `b` points to (a different object than the one that `a` points to)
print(b)
```
> `[1, 1, 1]`

## Starred Expressions (More with `*`!) and auto unpacking

You have seen `*` be used for a lot, but here is another thing that `*` is used for: starred expressions. In a colloquial sense, a starred expression "removes parentheses or brackets", but more specifically, it means that if `a` is a list or tuple (or any other collection), the python interpreter will interpret `*a` as the *actual python code* of its elements, comma separated. Here are some examples:

The `sum()`, `min()`, and `max()` functions can take any positive quantity of floats (or ints), or they can take a collection of floats and ints. Consider:
```python
min(1,2,3,4,5)
```
> `1`

or

```python
min([1,2,3,4,5])
```
> `1`

can be written instead like

```python
min(*[1,2,3,4,5])
```

The star turns the list of ints into a piece of python code which contains its contents, comma separated. Another example is the `print()` function, which takes any number of arguments and displays them (by default) with a single space separation. Notice the difference in output of

```python
print([1,2,3,4,5])
```
> `[1,2,3,4,5]`

and

```python
print(*[1,2,3,4,5])
```
> `1 2 3 4 5`

but see how the second example gives the same output as this!

```python
print(1,2,3,4,5)
```
> `1 2 3 4 5`

That is because `*[1,2,3,4,5]` becomes `1,2,3,4,5`!

One last example of starred expressions is an alternate way fo converting from a tuple to a list. We already reviewed how it might be done with `list()`, but here is another way:

```python
a = (1, 2, 3, 4, 5)
b = [*a]
print(b)
```
> `[1, 2, 3, 4, 5]`

Since `*a` is interpreted as the comma-separated elements of `a`, assigning `b = [*a]` is the same as assigning `b = [1, 2, 3, 4, 5]`, which is how you can make a list!

Python is very clean about the way that it handles multiple function arguments (which also involve the use of `*`), and we will certainly come back to this topic in the chapter on functions.

Very related to the idea of starred expressions is pythons capability to unpack collections into more than one variable at once. Imagine you have a tuple `(72, -26)` that represents an (x, y) coordinate. With the very easy use of auto-unpacking the tuple, you can assign the first element of the tuple to a variable `x`, and the second element to a variable `y` in just one step:

```python
x, y = (72, -26)
print(x)
print(y)
```
> `72`
>
> `-26`

This auto-unpacking works with any collection. In fact, even if you didn't have a collection, and you just wanted to assign two variables in the same line, python will let you do it!

```python
x, y = 72, -26
print(x)
print(y)
```
> `72`
>
> `-26`


## Which should I use?

The choice between different data structures is an important one to make as it can affect the speed and complexity of the programs you write. Generally, tuples are used as light-weight containers that can easily move around groups of information together, while lists are made to change over time. As you gain more experience with more of python's collections, the more comfortable of a programmer you will be.
