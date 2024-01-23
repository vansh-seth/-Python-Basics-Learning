# Python Basics
## Python Keywords and Identifiers

## Python Keywords

Keywords are predefined, reserved words used in Python programming that have special meanings to the compiler. We cannot use a keyword as a variable name, function name, or any other identifier. They are used to define the syntax and structure of the Python language.

All the keywords except `True`, `False`, and `None` are in lowercase and must be written as they are. The list of all the keywords is given below:

```
False   await     else     import     pass
None    break     except   in         raise
True    class     finally  is         return
and     continue  for      lambda     try
as      def       from     nonlocal   while
assert  del       global   not        with
async   elif      if       or         yield
```


## Python Identifiers

Identifiers are the names given to variables, classes, methods, etc. For example:

```python
language = 'Python'
```

Here, `language` is a variable (an identifier) that holds the value 'Python'. We cannot use keywords as variable names, as they are reserved names built into Python. For example:

```python
continue = 'Python'
```

The above code is incorrect because we have used `continue` as a variable name.

### Rules for Naming an Identifier

1. Identifiers cannot be a keyword.
2. Identifiers are case-sensitive.
3. They can have a sequence of letters and digits but must begin with a letter or `_`. The first letter of an identifier cannot be a digit.
4. It's a convention to start an identifier with a letter rather than `_`.
5. Whitespaces are not allowed.
6. Special symbols like `!`, `@`, `#`, `$`, etc., cannot be used.

### Some Valid and Invalid Identifiers in Python

| Valid Identifiers      | Invalid Identifiers |
|------------------------|----------------------|
| score                  | @core                |
| return_value           | return               |
| highest_score         | highest score        |
| name1                  | 1name                |
| convert_to_string      | convert to_string    |

### Things to Remember

- Python is a case-sensitive language. This means `Variable` and `variable` are not the same.
- Always give identifiers a name that makes sense. While `c = 10` is a valid name, writing `count = 10` would make more sense and be easier to understand.
- Multiple words can be separated using an underscore, like `this_is_a_long_variable`.


