# Conditionals

Until now, all of your programs have been completely linear. That is, each line was executed, starting from the top and continuing all the way to the bottom. However, it is very rare that linear programs like that will be useful. In this chapter we will learn about conditional expressions, where we can program decisions and choices. As you learn about more tools at a constant rate, the kinds of programs that you will be able to write will increase exponentially.

In the introduction chapter we discussed how indentation is very important to the python syntax. Until now, there has been no indentation and all of your programs have been written flush with the left side of your text editor. From now on, it is important to pay attention to not only the syntax of lines, but also to the syntax of code blocks.

Conveniently, python uses keywords to mark these decisions that are close to english grammar: `if`, `else`, and `elif` (else - if).

## `if` statements

Let's start with a basic `if` statement. The following code snippet shows the syntax:

```python
if BOOLEAN_CONDITION:
    EXECUTE_THIS
    CODE_BLOCK
```

As the variable names suggest, the statement that comes after the `if` must evaluate to a `boolean` type. For example, `5 > 2`, `True and False`, or `'f' in 'fun with conditionals'`. The `boolean` value us followed with a `:`. The code block indented below is executed if the `boolean` condition evaluates to `True`.

Here are some examples:

```python
if 1 < 2:
    print("My first if statement!")
```
> `My first if statement!`


```python
a = 5
if 3 < a:
    print(f"I print if 3 is less than {a}")

print("I print regardless")
```
> `I print if 3 is less than 5`
>
> `I print regardless`

Here is that same snippet, but with `a = 2`.

```python
a = 2
if 3 < a:
    print(f"I print if 3 is less than {a}")

print("I print regardless")
```
> `I print regardless`



## `if`-`else`

`if` statements alone only allow you to *decide whether* to execute certain blocks of code, but if you want to *decide between* blocks of code to execute, you can use `if`-`else`. Here is the syntax:

```python
if BOOLEAN_CONDITION:
    CODE_BLOCK
    NUMBER_ONE
else:
    CODE_BLOCK
    NUMBER_TWO
```

If the `boolean` condition is `True`, then code block one executes and code block two does not. If the condition is `False`, then code block one does not execute and code block two does. Here are some examples:

```python
a = 5
if 3 < a:
    print(f"I print if 3 is less than {a}")
else:
    print(f"I print otherwise (if 3 is greater than or equal to {a})")
```
> `I print if 3 is less than 5`



```python
a = 2
if 3 < a:
    print(f"I print if 3 is less than {a}")
else:
    print(f"I print otherwise (if 3 is greater than or equal to {a})")
```
> `I print otherwise (if 3 is greater than or equal to 2)`


```python
if "hello" in "HeLlO, WoRlD!".lower():
    print("hello is a substring")
else:
    print("hello is not a substring")
```
> `hello is a substring`


## `if`-`elif`-`else` (`if`-`else` chains)

`if`-`else` only allows you to decide between executing two code blocks, but using `elif` allows you to decide between executing any number of code blocks. `if` and `else` are only used once, but `elif` can be repeated. Here is the syntax:

```python
if CONDITION_ONE:
    CODE_BLOCK_ONE
elif CONDITION_TWO:
    CODE_BLOCK_TWO
.
.
.
elif CONDITION_Z:
    CODE_BLOCK_Z
else:
    FINAL_CODE_BLOCK
```

Only one of the code blocks above will execute. Note that the `else` at the end is optional, but if none of the `if` and `elif` conditions are `True`, none of the code blocks will execute. Here are some examples:

```python
a = True
b = False

if a and b:
    print("both")
elif a or b:
    print("one")
else:
    print("none")
```
> `one`


```python
a = 2

if a == 0:
    print("zero")
elif a == 1:
    print("one")
elif a == 2:
    print("two")
elif a == 3:
    print("three")
else:
    print("not zero, one, two, or three")
```
> `two`


**Remark.** If you have a procedure in mind, there are probably a few ways to code it. Sometimes, it is more clear to have nested code blocks and sometimes it is not. Here is an example of unnecessary nested code blocks and a cleaner alternative:


```python
a = 1

if a > 0:
    print("positive")
else:
    if a == 0:
        print("zero")
    else:
        print("negative")
```
> `positive`


is equivalent to


```python
a = 1

if a > 0:
    print("positive")
elif a == 0:
    print("zero")
else:
    print("negative")
```
> `positive`




## Ternary Statements

There are many situations when you want to make a small (in-line) decision in your program and it is easier to use a **ternary statement**. These statements make a decision about what to *evaluate to*. Here is the syntax:

```python
VALUE_ONE if CONDITION else VALUE_TWO
```

The value of the statement is `VALUE_ONE` if `CONDITION` is `True` and `VALUE_TWO` otherwise. Here is an example:

```python
a = 1 if 3 < 4 else 2
print(a)
```
> `1`

is equivalent to

```pythOn
if 3 < 4:
    a = 1
else:
    a = 2
print(a)
```
> `1`

It is possible to nest ternary statements, but excessive use of this can be confusing (see exercises).

## I lied about indentation before, but still don't do this

Earlier, I said that the code block that follows an `if` must be indented, and while this is best practice, it is not required. The following is also allowed (`;` separating lines in a code block).

```python
if 3 > 2: a = 1; b = 2; print("look, it works")

print(f"a = {a}, b = {b}")

```
> `look, it works!`
>
> `a = 1, b = 2`

Please, don't use this syntax.
