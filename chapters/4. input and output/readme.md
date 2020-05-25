# Input and Output

One of the most greatly useful things about python is how easy it is to interact with it. Both collecting user input and file interaction are very easy!


## `input()`

The `input()` function collects and returns user input from the standard input. When executed, input begins and is terminated by a newline character (pressing enter sends a newline character).

In python 3, input is is interpreted as a string and this string is returned. `input()` can take any argument that `print()` can take, and this argument is displayed as a prompt to the input. Here is an example:

```python
name = input("Enter your name: ")
print("Your name is " + name + ".")
```
> `Enter your name: ` peter
>
> `Your name is peter.`


## Opening and Closing Files

To open a file in python, you must first make sure you know the [relative path](https://en.wikipedia.org/wiki/Path_%28computing%29#Representations_of_paths_by_operating_system_and_shell) from the file you are writing the python in to the file you want to open.

The `open()` function takes two arguments, the file path and the open mode, both as a string. (There is an optional third argument that relates to binary file handling -- see Appendix for more details). Here is a table from W3Schools that summarizes different open modes:

| Mode   | Name    |  Description                                                                                |
|:------:|:-------:|:--------------------------------------------------------------------------------------------|
| `"r"`  | Read    | Default value. Opens a file for reading, error if the file does not exist                   |
| `"r+"` | Read    | Opens a file for reading and writing (overwrite first content), error if the file does not exist                      |
| `"a"`  | Append  | Opens a file for appending (add content), creates the file if it does not exist             |  
| `"a+"` | Append  | Opens a file for reading and appending (add content), creates the file if it does not exist |
| `"w"`  | Write   | Opens a file for writing (overwrite content), creates the file if it does not exist         |
| `"x"`  | Create  | Creates the specified file, returns an error if the file exists                             |

The mode determines the kind of *permission* that you have as you access the file. It is important to select the correct mode: choosing incorrectly can result in data loss.

`open()` returns a file object. Here is an example:

```python
f = open("path/to/myFile.txt", "r")
type(f)
```
> `<class '_io.TextIOWrapper'>`


Once you have your file object, you can call various methods on it. Use `read()` to return the contents of the file as a string:

```python
f = open("path/to/myFile.txt", "r")
f.read()
```
> `'contents of myFile.txt'`

An optional integer argument to `read()` can specify the number of characters to read from the file.

The function `readline()` will read a line from the file: `f.readline()` will return the first substring of `f.read()` up until a newline character that has not been read yet. Successive calls to `readline()` will result in successive lines being printed. Here is a large example:

```python
f = open("path/to/poem.txt", "r") # contains "Dreams" by Langston Hughes
print("The result of f.read():")
print(f.read())

print("---" * 10)

print("calling f.readline() three times")
f.readline()
f.readline()
f.readline()
```
> `Hold fast to dreams`
>
> `For if dreams die`
>
> `Life is a broken-winged bird`
>
> `That cannot fly.`
>
> `Hold fast to dreams`
>
> `For when dreams go`
>
> `Life is a barren field`
>
> `Frozen with snow.`
>
> `------------------------------`
>
> `Hold fast to dreams`
>
> `For if dreams die`
>
> `Life is a broken-winged bird`


Once you are done with a file it is important to close it. This is done by calling `close()`:

```python
f = open("path/to/myFile.txt")
f.read()
f.close()
```

A safe way to open a file and automatically close it is to use a "`with` `open` `as`". Here is the syntax:

```python
with open(path, mode) as f:
    CODE_BLOCK_TO_DO
    SOMETHING_WITH_THE_FILE
```

is equivalent to (but much safer than)


```python
f = open(path, mode)
CODE_BLOCK_TO_DO
SOMETHING_WITH_THE_FILE
f.close()
```


## Editing Files


If you are in read mode, you cannot change the file you have opened. To change the content of a file, you must open it in either write or append mode.

The following code uses `write()` to append a line to the file `myFile.txt`

```python
with open ("path/to/myFile.txt", "a") as f:
    f.write("some text")
```

and this code replaces the content of `myFile.txt`.

```python
with open ("path/to/myFile.txt", "w") as f:
    f.write("some text")
```

 The only difference is the mode! The same code but with mode `"r+"` will only overwrite the first 9 characters with the new text (since "some text" is nine characters long).

The mode `"a+"` can also be used to append, but also read, starting from the beginning of the file! For that reason, `"a+"` is a very safe mode to open a file in.


## Creating and Deleting files and folders

To create a file, use the mode `"x"`, `"a"`, `"a+"` or `"w"`. The following code creates a file called "myNewFile.txt":

```python
open("myNewFile.txt", "a+")
```

Python can be used to delete files and folders on your computer with the `os` module:

```python
import os
os.remove("deleteMe.txt")
```


Remove a folder with `os.rmdir()`:

````python
import os
os.rmdir("myFolderToDelete")
```
