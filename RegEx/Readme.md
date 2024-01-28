# Python RegEx

A Regular Expression (RegEx) is a sequence of characters that defines a search pattern. For example,

```
^a...s$
```

The above code defines a RegEx pattern. The pattern is: any five-letter string starting with a and ending with s.

A pattern defined using RegEx can be used to match against a string.

| Expression | String   | Matched? |
|------------|----------|----------|
| ^a...s$    | abs      | No match |
|            | alias    | Match    |
|            | abyss    | Match    |
|            | Alias    | No match |
|            | An abacus| No match |

Python has a module named re to work with RegEx. Here's an example:

```python
import re

pattern = '^a...s$'
test_string = 'abyss'
result = re.match(pattern, test_string)

if result:
    print("Search successful.")
else:
    print("Search unsuccessful.")    
```

Here, we used `re.match()` function to search the pattern within the `test_string`. The method returns a match object if the search is successful. If not, it returns None.

There are other several functions defined in the `re` module to work with RegEx. Before we explore that, let's learn about regular expressions themselves.

If you already know the basics of RegEx, jump to Python RegEx.

### Specify Pattern Using RegEx

To specify regular expressions, metacharacters are used. In the above example, `^` and `$` are metacharacters.

#### MetaCharacters

Metacharacters are characters that are interpreted in a special way by a RegEx engine. Here's a list of metacharacters:

- `[]` - Square brackets

Square brackets specify a set of characters you wish to match.

| Expression | String    | Matched? |
|------------|-----------|----------|
| `[abc]`    | a         | 1 match  |
|            | ac        | 2 matches|
|            | Hey Jude  | No match |
|            | abc de ca | 5 matches|

Here, `[abc]` will match if the string you are trying to match contains any of the a, b, or c.

You can also specify a range of characters using `-` inside square brackets.

- `[a-e]` is the same as `[abcde]`.
- `[1-4]` is the same as `[1234]`.
- `[0-39]` is the same as `[01239]`.

You can complement (invert) the character set by using caret `^` symbol at the start of a square bracket.

- `[^abc]` means any character except a, b, or c.
- `[^0-9]` means any non-digit character.

- `.` - Period

A period matches any single character (except newline '\n').

| Expression | String | Matched? |
|------------|--------|----------|
| `..`       | a      | No match |
|            | ac     | 1 match  |
|            | acd    | 1 match  |
|            | acde   | 2 matches|

```
