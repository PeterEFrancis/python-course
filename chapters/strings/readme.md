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
>
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

In python, strings are immutable objects, meaning that they *cannot* be changed.
```python
a = "Foo" # a points to "Foo"
b = a # b points to the same "Foo" that a points to
a = a + a # a points to the new string "FooFoo", but b still points to the old "Foo"
print(a)
print(b)
```
Observe that `b` hasn't changed, even though `a` has; the string literal objects `"Foo"` and `"FooFoo"` have not changed.

We can use `*` to create repeated strings as follows:

```python
print("abc" * 3)
```
> `abcabcabc`


## Casting

Sometimes we wish to treat a nonstring as a string. Here is an example.

```python
my_num = 2
print(f"my_num is {my_num}")
print("my_num is " + str(my_num))
```
> `my_num is 2`
>
> `my_num is 2`

`str` is the *conversion function* that returns a string representation of any python object. We will return to `str` in the chapter on classes.

In the first chapter, we used `int()` to convert other numeric types to `int`s. `int` can also make an integer from a string literal that contains an integer (surrounding whitespace is ok).

```python
x = int('3 ')
type(x)
```
> `<class 'int'>`

In fact, `int()` has an optional second argument, that specifies the base to interpret the integer in the string as (and convert into base 10). The possible base numbers are inclusivelty between 2 and 36, and 0.

The following will convert the base 6 number `'123450'` to base 10.

```python
int('123450', 6)
```
> `11190`

## Splitting strings

* indexing (s[0])
* basic slicing (s[1:5])
* advanced slicing (s[0:10:2])
* reversing (s[::-1])

## <u>Bonus</u>: UTF-8 (special characters are allowed in strings (emoji, crazy characters))

Note that in python, strings are always encoded correctly with Unicode, meaning that all sorts of "special" characters like emoji, diacritics, and Chinese characters are able to be used and will print correctly.

For the most part, strings can be treated as lists of individual characters. However, in lots of weird edge cases, this can break down:

```python
s = "z̸̢̢̧̧͕̞̱͍͉̯̰͍̞͙͔̪͈̬̬̞̋̎̄̿͑̐̑͐̄̌̅̋̅̅̄̀́̏̈a̷̢̬̥̱̜͒̂́̊͑̿͊̽̅̍͊͘͘͘͠l̵̢̧̨͍̜̰̦̼̬͍̹͚͔̗͈͈̩͇͉̞̼̗̮͚͂̒̂̅́͗̚̚ͅg̴̡̨̻̪̻̼͉̲̜̹̐̂̉̒̈́͋͋̍͆̇̓̂̄͛̊̉̓̾̚͝͝͝o̴͍̟̜͙͓̮͕͙̦̙̟͂̐͌̋̂͛̈̄̒͊͂͘̕ ̵͚̪̖̖̲̖̝̱̫̯̪͌͑̽̍́͆̆̿̊̕͠c̷͚̪͖̏̀̒̆͋̂͛̀̀́̽͠o̴̘̰̣̬͍͆͒̊̎̃͠m̶̧̨̰̜̟̞̲̖̣͍͈̜̤̤̝̬͙͓̼̠͇̘̹̩̙̼̀̊̃̀̉̆̂̆̀̊̀̔̈́̐͜ȩ̵̠͕̗̠̼̣̰͕̙͍̖̙͖̳̩̟̘͑͆̋̿̄͂͒̏̂̍͋̄̎͆́̓͝ş̴̟̗̦̣̪̩̣͎͈̗͕̾͐̈́͋͐͛̀͊̆͋̅͌͑͘̚͝"
print(s[0])  # print the first character in s
```
> `z`

However, python will take care of string encoding for you, and will typically handle things sanely.
