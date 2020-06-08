# `while` Loops

Loops are used to repeatedly execute code blocks. Python has two types of loops: `while` loops and `for` loops. In this chapter we will learn about `while` loops, which you will see are closely related to `if` statements.

## The Basic `while` Loop

A basic `while` loop will repeatedly execute its body code block while a condition is `True`, stopping only when the condition becomes `False`. Here is the syntax:

```python
while CONDITION:
  CODE_BLOCK_TO
  EXECUTE_WHILE_THE
  CONDITION_IS_TRUE
```

It is very important to note when using loops that it is possible to create an **infinite loop**, which will never terminate. This can crash your computer and should be avoided by always making sure that your loop's condition will eventually be `False`. The canonical example of an infinite loop is

```Python
while True:
  pass
```

Note that `pass` is a python keyword meaning "do nothing here". Since certain statements (like `while` loops) require indented code blocks, `pass` is the useful way to make an "empty" code block.


In the following example, we use a `while` loop to print out the positive integers less than 5:

```python
i = 1
while i < 5:
  print(i)
  i += 1
```
> `1`
>
> `2`
>
> `3`
>
> `4`

The value of `i` increases by one during every execution of the loop's body. When `i` is 5, the condition `i < 5` is `False`, so the loop terminates. Note that if we did not increment `i` in the body of the loop, we would have created an infinite loop that would continuously print `1`. Here is another example of a while loop with a bit more in its body:

```python
string = "Hello. My name is Peter and this is a while loop."
while string.count("e") != 0:
    first_e = string.find("e")
    string = string[:first_e] + "E" + string[first_e + 1:]
print(string)
```
> `HEllo. My namE is PEtEr and this is a whilE loop.`

This loop capitalizes every `E`. This can also be done by calling `string.replace("e", "E")`. The following example is similar, but can not be done with a simple string method:

```python
string = "Hello. My name is Peter and this is a while loop."
i = 1
while string.count("e") != 0:
    first_e = string.find("e")
    string = string[:first_e] + str(i) + string[first_e + 1:]
    i += 1
print(string)
```
> `H1llo. My nam2 is P3t4r and this is a whil5 loop.`

This loop replaces every `e` with the the value of `i`, which gets incremented every time an `e` is found.



## The `break` Statement

The break statement can be used to break from a loop when the loop condition is still true. Usually, `break` is called inside a conditional. The following example is a modification of the first:

```python
i = 1
while i < 5:
  if i == 3:
    break
  print(i)
  i += 1
```
> `1`
>
> `2`

As you can see, the loop ended when `i` was `3`, even though the loop condition `i < 5` was still `True`. `break` statements can be used to exit a loop on a condition that is different than (or is too difficult to incorporate into) the loop condition. This might happen if you wish to break out of a loop at more than one point in the code block.

Here is another example of breaking on a different condition than the loop condition:

```python
s = ""
i = 1
while i < 10:

  t = ""
  if i % 3 == 0:
    t = "a"
  elif i % 3 == 1:
    t = "bc"
  else:
    t = "def"

  s += t * i

  if len(s) >= 20:
    break

  i += 1

print(s)
```
> `bcdefdefaaabcbcbcbc`

## `break`-`else`

The `else` keyword is also used in the context of loops in order to distinguish a code block that is executed only when the associated while loop is not broken out of. That is, the `else` code block is executed at the end of the while loop if `break` was never called during the loop's execution. Here are some examples:

```python
i = 0
while i < 10:
  i += 1
  if i == 5:
    break
  print(i)
else:
  print("the loop never broke")
```
> `1`
>
> `2`
>
> `3`
>
> `4`

```python
i = 0
while i < 5:
  i += 1
  if i == 10:
    break
  print(i)
else:
  print("the loop never broke")
```
> `1`
>
> `2`
>
> `3`
>
> `4`
>
> `5`
>
> `the loop never broke`

```python
i = 0
while i < 5:
  i += 1
  print(i)
else:
  print("there was no break statement, so I execute anyway")
```
> `1`
>
> `2`
>
> `3`
>
> `4`
>
> `5`
>
> `there was no break statement, so I execute anyway`




## The `continue` Statement

The `continue` statement is used to stop the current iteration and *continue* on to the next one (if the loop condition is still satisfied). Here is an example:


```python
i = 0
while i < 5:
  i += 1
  if i == 3:
    continue
  print(i)
```
> `1`
>
> `2`
>
> `4`
>
> `5`

When using a `while` loop it is important to consider the location of the lines that potentially change the loop condition: in this case, `i += 1`. Consider the following code snippet, which at first glance, may seem to be equivalent to the one above. However, this code will cause an infinite loop:

```python
i = 1
while i < 5:
  if i == 3:
    continue
  print(i)
  i += 1
```

During the iteration of the loop when `i` is `3`, `continue` is called, so the loop moves to the next iteration, but `i` is still `3`. Since `i` is never incremented, `i < 5` will never be `False`, so the loop will continue indefinitely.
