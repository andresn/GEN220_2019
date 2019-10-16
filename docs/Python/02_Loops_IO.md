# Logic, Loops and Input/IO

Looping through data and reading in files or writing out to files.

There are many Python functions available to do many things. Here is a link to list of many of these [https://docs.python.org/3/library/functions.html](https://docs.python.org/3/library/functions.html).


## Logic

In python if statements end with `:` and Indentation is required.
This indentation can be with spaces or tabs, but not a mix of each.


```python
if TRUE:
    THEN DO X
elif OTHER_THING_TRUE:
    THEN DO Y 
else:
    THEN DO Z
```


## Loops

Loops let you 
```python
while ( TRUE ):
    Do X
for ITERATOR in LIST:
    Do Y
for i in range(5):
    print(i)
```

## Python Indentation

Most editors do this automatically but you might find it hard to
detect errors looking at the code until you try to run it if there are
tabs in one part and sapces in another.

This indentation can be either spaces or tabs. Emacs/Atom/Vi allow
customizing your editor so that when [tab] is typed it will either
insert 4 spaces or a tab. Switching between editors while editing a
file can sometimes cause problems.

Solution: delete the indendentation and enter the tab (or spaces) again.

After this slide you will now understand this scene from [Silicon Valley](https://www.youtube.com/watch?v=SsoOG6ZeyUI).

## Logic operators

To test if somehting is equal use `==` or `is`.
```python
x=10
if x == 10:
        print("this == 10")
if x == "10":
        print("this == '10'")
if x is 10:
        print("this is a 10")
if x is "10":
        print("This is '10'")
```
