# Introduction

Python is a great (first) language to learn. Its simple and clutter-free syntax allows you to focus on learning the logic of programming. Python is also widely applicable: you're really getting a bang for your buck!

In this introduction, I will review the structure of this repository and some very basic information for working with python and Jupyter Notebooks.

## Git and GitHub

Git and GitHub repositories are a huge topic, so right now we will just be concerned with what we need to be in order to use them. Here is a simplistic take: you can think of a repository as a folder of files that includes a special hidden file. Every time you "commit" a change, the hidden file rememebers what you did. You can (and you should frequently) "push" your repositories that you have saved locally on your computer, to GitHub. By pushing to GitHub, the changes that are saved in that secret file are made to the version of the repository that is on GitHub. You can also "pull" changes from GitHub, which makes any changes that were made to the GitHub version of the repository to your personal repository. This should be your mantra in order to not lose work: "pull, edit, push, repeat"! This way, if something goes wrong with your local git repository, the wrost case senario is that you delete it and then just "clone" another copy from GitHub. Again, there is a LOT more to go into about Git and GitHub, but We will save that for another day.


## The Structure of This Respository

You will create your own repository that you have acces to edit. You will also be able to see my repository for this course (it's what you are looking at right now!) but you wont be able to make changes to it.

In each chapter folder there is a "material.md" and an "exercises.md" file. As the names would suggest, the "material.md" file contains the information for that chapter, and the "exercises.md" contains the exercises.

In "material.md", there will occasionally be links that direct you to another site to do some short reading.

I denote code and the output of the code like this:

```python
print("Hello, World!")
```
> `Hello, World!`


## Basic Info

You will be completing exercises coding in python in Jupyter notebooks, which are files with multiple cells. Each cell can have one of three formats: code, markdown, or raw text. That is, each cell may either be used to execute python code, write styled and formatted text, or diplay plain text. For the most part, we will be using code and markdown cells.

Markdown is a very simple language (this is written in markdown) that you can learn about quickly here: https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet. Some exercises will ask that you use markdown to respond to a question.

As a very introductory lesson in python syntax, there are four important takeaways:

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

3. When python code executes, it is read code block by code block, if the last line with zero indentation has a value, that value will be displayed. If you wish for something in the middle of a block of code to be displayed, use `print()`. For example,
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

4. When a bit of python is executed (interpreted and run by the computer), we can tell the interpreter to ignore certain lines or bits of code using comments. The symbol to start a comment is `#`, meaning that everything on the line after a `#` symbol is ignored. For example,

```python
print(1)
# print(2)
print(3)
```
> `1`
>
> `3`

only prints 1 and 3 because the line that calls 2 to print is commented out. Comments are an important part of coding: not only do they allow you to leave notes to yourself and others who are reading your code, but they are also a good way to temporarily remove code to try and find errors.
