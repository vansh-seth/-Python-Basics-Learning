# Python File I/O

A file is a container in computer storage devices used for storing data.

When we want to read from or write to a file, we need to open it first. When we are done, it needs to be closed so that the resources that are tied with the file are freed.

Hence, in Python, a file operation takes place in the following order:

1. Open a file
2. Read or write (perform operation)
3. Close the file

## Opening Files in Python

In Python, we use the `open()` method to open files.

To demonstrate how we open files in Python, let's suppose we have a file named `test.txt` with some content.

```python
# open file in current directory
file1 = open("test.txt")
```

By default, files are opened in read mode (`"r"`). The code above is equivalent to:

```python
file1 = open("test.txt", "r")
```

### Different Modes to Open a File in Python

| Mode | Description |
| ---- | ----------- |
| r    | Open a file for reading. (default) |
| w    | Open a file for writing. Creates a new file if it does not exist or truncates the file if it exists. |
| x    | Open a file for exclusive creation. If the file already exists, the operation fails. |
| a    | Open a file for appending at the end of the file without truncating it. Creates a new file if it does not exist. |
| t    | Open in text mode. (default) |
| b    | Open in binary mode. |
| +    | Open a file for updating (reading and writing) |

## Reading Files in Python

After opening a file, we use the `read()` method to read its contents. For example,

```python
# open a file
file1 = open("test.txt", "r")

# read the file
read_content = file1.read()
print(read_content)
```

## Closing Files in Python

When we are done with file operations, we need to properly close the file using the `close()` method. For example,

```python
# open a file
file1 = open("test.txt", "r")

# read the file
read_content = file1.read()
print(read_content)

# close the file
file1.close()
```

## Exception Handling in Files

A safer way to handle file closing is to use a `try...finally` block.

```python
try:
    file1 = open("test.txt", "r")
    read_content = file1.read()
    print(read_content)
finally:
    # close the file
    file1.close()
```

## Use of `with...open` Syntax

In Python, we can use the `with...open` syntax to automatically close the file.

```python
with open("test.txt", "r") as file1:
    read_content = file1.read()
    print(read_content)
```

## Writing to Files in Python

To write to a file in Python, we need to open it in write mode (`"w"`). If the file doesn't exist, a new file is created.

```python
with open('test2.txt', 'w') as file2:
    # write contents to the test2.txt file
    file2.write('Programming is Fun.')
    file2.write('Programiz for beginners')
```

## Python File Methods

Here are some commonly used file methods:

- `close()`
- `flush()`
- `read()`
- `readline()`
- `readlines()`
- `write()`
- `writelines()`

These methods help in performing various operations on files.
