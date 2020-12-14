# Introduction Exercises

This exercise will teach you the process you will go through when you are completing any other set of exercises. You will do this once per chapter and it might seem tedious at first, but you will get used to it and soon it will be fun!


1. The process is slightly different for MacOS and Windows users:
  - (MacOS) Open a terminal window and run the line
    ```bash
    jupyter notebook
    ```
    This will start a local server on your computer and load a webpage at something like "http://localhost:8891/tree". This webpage is just a fancy file browser in your web browser. Click "Programming" and then click "learning-python".
  - (Windows)
    Open PyCharm and open the "learning-python" project. Click the "Terminal" button on the bottom left of the window and type
    ```bash
    jupyter notebook
    ```
    Copy and paste the link that is generated into a browser. This page is a file browser.

2. Click the "New" dropdown button and select "Python 3". This will create a new jupyter notebook.
3. Rename this notebook with the title of the chapter that the exercises are for by clicking the current name. In this case, name the notebook "introduction".
4. Make the first cell a markdown cell with the dropdown menu, and make a "H1" heading that is the name of the chapter you are working on. In this case, type
```markdown
# introduction
```
5. Execute the cell to render the markdown by pressing "shift + enter" ("shift + return" on mac) or clicking the "Run" button.
6. Make sure that the next cell is a code cell by inspecting the drop down.
7. Type the following and execute the cell
  ```python
  print("Hello, World!")
  ```
  You should see an output:
  > `Hello, World!`

8. In the next cell, copy what you had in the previous cell and paste it three times.
9. Replace the "Hello, World!" text with something else (you could write a haiku!).
10. Add comments to the cell about whatever you would like, perhaps commenting on things you notice about jupyter or python so far.
11. Create another cell below the last one and change it to a markdown cell.
12. Write some markdown that uses at least five different styles. **Hint:** how do you underline, italicize, etc. ?
13. Save the document.
14. Return to Atom/PyCharm to commit your changes and push them to GitHub.
