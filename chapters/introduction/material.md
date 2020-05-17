# Introduction

In this introduction, I will go over the structure of this repository as well as some very basic info for working with python and Jupyer Notebooks.

## The structure of this respository

In each chapter folder there is a "material.md" and an "exercises.md" file. As the names would suggest, the "material.md" file contains the iformation for that chapter, and the "exercises.md" contains the exercises.

In "material.md", there will occasionally be links that direct you to anoter site to do some short reading.

As you read, I denote code and the output of the code like this:

```python
print("Hello, World!")
```
> `Hello, World!`


## Basic Info

Python is a great (first) language to learn. Its simple and clutter free syntax allows you to focus on learning the logic of programming. Python is also widely applicable: you're really getting a bang for your buck!

You will be completing exercises coding in python in jupyter notebooks, which are files with multiple cells. Each cell can have one of three formats: code, markdown, or raw text. That is, each cell may either be used to execute python code, write styled and formatted text, or diplay plain text. We will be mostly using the first two formats.

Markdown is a very simple language (this is written in markdown) that you can learn about quickly here: https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet. Some exercises will ask that you use markdown to respond to a question.

As a very introductory lesson in python syntax, there are four important take-aways:

1. Python can be used as a console: like a fancy calculator, it waits for input and executes the input as it comes. Python can be given large blocks of code to execute together.

2. In python, *indentation* matters. Some other languages use nested braces to destinguish blocks of code, but in python it is only indentation, which helps readability a lot! For example,
```python
if 3 < 5:
  print("three is less than five")
```
> `three is less than five`

is valid python syntax, while
```python
if 3 < 5:
print("three is less than five")
```
is not! We will learn about what this code is doing in particular later on.
3. When python code executes, it is read code-block by code-block, if the last line with zero indentation has a value, that value will be displayed. If you wish for something in the middle of a block of code to be displayed, user `print()`. For example,
```python
1
print(2)
3
4
5
```
> `2`
>
> `5`

4. When a bit of python is executed (interpreted and run by the computer), we can tell the interpreter to ignore certain lines or bits of code using comments. The symbole to start a comment is `#`, meaning that everything on a line after a `#` symbol is ignored. For example,

```python
print(1)
# print(2)
print(3)
```
> `1`
>
> `3`

only prints 1 and 3 because the line that calls 2 to print is commented out.
