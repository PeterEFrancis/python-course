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

## Escaping

To create multiline strings, use three sets of quotation marks like this

```python
print("""bacon
bacon""")
```
> `bacon`
>
> `bacon`

Using only one set of quotation marks will cause an error.

```
print("bacon
bacon")
```

Another way to accomplish this is to use the *escape code* \n in our string:

```python
print("bacon\nbacon")
```
> `bacon`
>
> `bacon`


There is a large variety of escape codes that allow us to handle characters that are otherwise too difficult to include in string literals. The most commonly used examples in python are:

| code          | meaning                  |
|:-------------:|:------------------------:|
| `\n`          | new line                 |
| `\t`          | tab                      |
| `\\`          | backslash character (\\) |
| `\'` and `\"` | quote marks              |


## String operations

To add (or *concatenate*) two strings, use a `+` sign:

```python
str_one = "Foo"
str_two = "Bar"
print(str_one + str_two)
```
> `FooBar`

In python, strings are immutable objects, meaning that they *cannot* be changed.

```python
a = "Foo"   # a points to "Foo"
b = a       # b points to the same "Foo" that a points to
a = a + a   # a points to the new string "FooFoo", but b still points to the old "Foo"
print(a)
print(b)
```
Observe that `b` hasn't changed, even though `a` has; the string literal objects `"Foo"` and `"FooFoo"` have not changed.

We can use `*` to create repeated strings as follows:

```python
print("abc" * 3)
```
> `abcabcabc`


We can use `==` to check if two strings **contain the same characters**:

```python
"FooBar" == "FooBar"
```
> `True`


```python
"FooBar" == "foobar"
```
> `False`


## Casting

In the first chapter, we used `int()` to convert other numeric types to `int`s. `int` can also make an integer from a string literal that contains an integer (surrounding whitespace is ok).

```python
x = int('3 ')
type(x)
```
> `<class 'int'>`

In fact, the *conversion function* `int()` has an optional second argument, that specifies the base to interpret the integer in the string as (and convert into base 10). The possible base numbers are inclusively between 2 and 36, and 0.

The following will convert the base 6 number `'123450'` to base 10.

```python
int('123450', 6)
```
> `11190`


The `float()` conversion function can take a string and return a `float()`:

```python
x = float("1.234")
type(x)
```
> `<class 'float'>`

Note that whitespace at the ends is ok!

The `complex()` conversion function operates similarly:

```python
x = float("1.2+3.4j")
type(x)
```
> `<class 'complex'>`


**Warning:** You may be tempted to spaces next to the `+` like this `complex("1 + 2j")`. This is not allowed!


## Formatting Strings

Sometimes we wish to treat a non-string as a string. Here is an example.

```python
my_num = 2
print(f"my_num is {my_num}")
print("my_num is " + str(my_num))
```
> `my_num is 2`
>
> `my_num is 2`

`str` is the conversion function that returns a string representation of any python object. We will return to `str` in the chapter on classes.

There are a few other ways to take a non-strings and format it like (or in) a string. One very simple way is to use an `f` and `{}`. Here is an example:

```python
f"The things inside {1} the braces {1 + 1} are evaluated."
```
> `'The things inside 1 the braces 2 are evaluated.'`


This is actually a very large topic in of itself, but for the most part, you will be content with the information presented here about formatting strings. If you find yourself in needing more or you are just curious, here is a good resource: https://pyformat.info/ to learn about all of the cool things you can do!



## Splitting strings

One common use of strings is to select parts of them. Square brackets are used to access characters of the string.

Before showing an example of this, it is important to understand that python has **zero-based indexing** meaning that the first element is accessed with a 0. This may be weird to begin with, but it will eventually become natural to begin counting with zero.

Ok, here are some examples of **indexing**:

```python
print("hello"[2])
```
> `l`


```python
a = "this is some text"
b = a[4]
b
```
> `' '`

```python
c = "bacon"
c[0]
```
> `'b'`


Instead of just getting a character of a string, we can get a **slice** by using a `:` and two indices of the string:

```python
print("abcdefgh"[2:6])
```
> `cdef`

Note that the first index is *inclusive* and the second is *exclusive*.

One more parameter in the square bracket determines by how much the slice skips over characters

```python
print("abcdefgh"[2:6:2])
```
> `ce`

If this last (optional) parameter is negative, the character selection will go in reverse (make sure that the first two parameters are also switched to go in reverse order):

```python
print("abcdefgh"[4:1:-2])
```
> `ec`


If you do not include one of the first two parameters, the slicing will default to the beginning or the end of the string, depending on the sign of the first term. One common use of this is to reverse strings:

```python
print("em esrever"[::-1])
```
> `reverse me`


## `len()` and `in`

Here are two very useful and somple things that you can do with strings:

Use the `len` function to find the length of a string (the number of characters).

```python
len("hello, my name is $*!#@")
```
> `23`

You can use the `in` keyword to check whether or not a string is a substring of another string:

```python
"llo, m" in "hello, my name is $*!#@"
```
> `True`

```python
"llo, m" not in "hello, my name is $*!#@"
```
> `False`


```python
not "llo, m" in "hello, my name is $*!#@"
```
> `False`


## String Methods

There are many useful functions that can operate on strings in a little bit of a different way than you have seen before. Instead of taking the string as a parenthetical argument, these methods (another word for function) uses this format: `string.method()`.

The string method `strip()` removes whitespace and newline characters from the ends of strings.

```python
"            not a lot of whitespace             ".strip()
```
> `'not a lot of whitespace'`

The `lower()` and `upper()` methods do exactly what you would expect:

```python
"make me upper case".upper()
```
> `'MAKE ME UPPERCASE'`

```python
"MAKE ME LOWERCASE".lower()
```
> `'make me lowercase'`

These two methods have boolean counterparts `isupper()` and  `islower()`:


```python
"I cAn\'T mAkE uP My mInD".isupper()
```
> `False`

```python
"I cAn\'T mAkE uP My mInD".islower()
```
> `False`

```python
"I AM ALL CAPTITAL!".isupper()
```
> `True`

Notice that "!" is not an uppercase letter. So why did `isupper()` evaluate to `True`? Well, both `isupper()` and `islower()` only check if all letters are uppercase or lowercase, respectively.  

```python
"I 1 AM 2 ALL 3 CAPTITAL 4 TOO!".isupper()
```
> `True`

These are just the highlights; we will be returning to different string methods often. You will become familiar with more very soon (see exercises).





<!-- ## <u>Bonus</u>: UTF-8 (special characters are allowed in strings (emoji, crazy characters))

Note that in python, strings are always encoded correctly with Unicode, meaning that all sorts of "special" characters like emoji, diacritics, and Chinese characters are able to be used and will print correctly.

For the most part, strings can be treated as lists of individual characters. However, in lots of weird edge cases, this can break down:

```python
s = "z̸̢̢̧̧͕̞̱͍͉̯̰͍̞͙͔̪͈̬̬̞̋̎̄̿͑̐̑͐̄̌̅̋̅̅̄̀́̏̈a̷̢̬̥̱̜͒̂́̊͑̿͊̽̅̍͊͘͘͘͠l̵̢̧̨͍̜̰̦̼̬͍̹͚͔̗͈͈̩͇͉̞̼̗̮͚͂̒̂̅́͗̚̚ͅg̴̡̨̻̪̻̼͉̲̜̹̐̂̉̒̈́͋͋̍͆̇̓̂̄͛̊̉̓̾̚͝͝͝o̴͍̟̜͙͓̮͕͙̦̙̟͂̐͌̋̂͛̈̄̒͊͂͘̕ ̵͚̪̖̖̲̖̝̱̫̯̪͌͑̽̍́͆̆̿̊̕͠c̷͚̪͖̏̀̒̆͋̂͛̀̀́̽͠o̴̘̰̣̬͍͆͒̊̎̃͠m̶̧̨̰̜̟̞̲̖̣͍͈̜̤̤̝̬͙͓̼̠͇̘̹̩̙̼̀̊̃̀̉̆̂̆̀̊̀̔̈́̐͜ȩ̵̠͕̗̠̼̣̰͕̙͍̖̙͖̳̩̟̘͑͆̋̿̄͂͒̏̂̍͋̄̎͆́̓͝ş̴̟̗̦̣̪̩̣͎͈̗͕̾͐̈́͋͐͛̀͊̆͋̅͌͑͘̚͝"
print(s[0])  # print the first character in s
```
> `z`

However, python will take care of string encoding for you, and will typically handle things sanely. -->
