# Strings

## Basics

Strings are sequences of characters which can be of any length, and are constructed using *string literal syntax*, surrounding some text in your code with quote marks.

```python
my_str = "hello there!"
print(my_str)
```

Note that in python, double quote marks, such as in:

```python
"Hello, world!"
```
are exactly the same as single quote marks:

```python
'Hello, world!'
```

## Escaping (\n, \t, etc.)

There are certain characters that are too difficult to include in string literals. For example, if we wanted to have a string which contains the word "bacon" twice, each on different lines:

```
bacon
bacon
```

We *can't* include the line break in the string:

```
print("bacon
bacon")
```

To make the string properly, we'll need to use the *escape code* \n in our string:

```python
print("bacon\nbacon")
```
> `bacon`
> `bacon`

The most commonly used escape codes in python are:

| code | meaning |
|:----:|:-------:|
| `\n`  | new line |
| `\t`  | tab      |
| `\\`  | backslash character (\)|
| `\'` and `\"` | quote marks |


## String operations (adding strings together, equality, formatting?)

To add (or *concatenate*) two strings, use a `+` sign:

```python
str_one = "Foo"
str_two = "Bar"
print(str_one + str_two)
```
> `FooBar`

In python, strings are mutable objects, meaning that they *can* be changed.

```python
my_num = 2
print(f"my_num is {my_num}")
print("my_num is " + str(my_num))
```
> `my_num is 2`
> `my_num is 2`

Notice that `str` is the *conversion function* that converts anything into a string.

## Splitting strings

## UTF-8 (special characters are allowed in strings (emoji, crazy characters))
