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

### Specify Pattern Using RegEx

To specify regular expressions, metacharacters are used. In the above example, `^` and `$` are metacharacters.

#### MetaCharacters

Metacharacters are characters that are interpreted in a special way by a RegEx engine. Here's a list of metacharacters:

```
[] . ^ $ * + ? {} () \ |
```

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


- `^` - Caret

Used to check if a string starts with a certain character.

| Expression | String | Matched? |
|------------|--------|----------|
| ^a         | a      | 1 match  |
|            | abc    | 1 match  |
|            | bac    | No match |
| ^ab        | abc    | 1 match  |
|            | acb    | No match (starts with a but not followed by b) |


- `$` - Dollar

Used to check if a string ends with a certain character.

| Expression | String  | Matched? |
|------------|---------|----------|
| a$         | a       | 1 match  |
|            | formula | 1 match  |
|            | cab     | No match |

- `*` - Star

Matches zero or more occurrences of the pattern left to it.

| Expression | String | Matched? |
|------------|--------|----------|
| ma*n       | mn     | 1 match  |
|            | man    | 1 match  |
|            | maaan  | 1 match  |
|            | main   | No match (a is not followed by n) |
|            | woman  | 1 match  |

- `+` - Plus

Matches one or more occurrences of the pattern left to it.

| Expression | String | Matched? |
|------------|--------|----------|
| ma+n       | mn     | No match (no 'a' character) |
|            | man    | 1 match  |
|            | maaan  | 1 match  |
|            | main   | No match (a is not followed by n) |
|            | woman  | 1 match  |

- `?` - Question Mark

Matches zero or one occurrence of the pattern left to it.

| Expression | String | Matched? |
|------------|--------|----------|
| ma?n       | mn     | 1 match  |
|            | man    | 1 match  |
|            | maaan  | No match (more than one 'a' character) |
|            | main   | No match (a is not followed by n) |
|            | woman  | 1 match  |


- `{}` - Braces

Consider this code: {n,m}. This means at least n, and at most m repetitions of the pattern left to it.



| Expression | String     | Matched? |
|------------|------------|----------|
| a{2,3}     | abc dat    | No match |
|            | abc daat   | 1 match  |
|            | aabc daaat | 2 matches (at aabc and daaat) |
|            | aabc daaaat| 2 matches (at aabc and daaaat) |

The RegEx [0-9]{2, 4} matches at least 2 digits but not more than 4 digits.

| Expression | String        | Matched? |
|------------|---------------|----------|
| [0-9]{2,4} | ab123csde     | 1 match  |
|            | 12 and 345673 | 3 matches (12, 3456, 73) |
|            | 1 and 2       | No match |

- `|` - Alternation

The vertical bar | is used for alternation (or operator).

| Expression | String  | Matched? |
|------------|---------|----------|
| a\|b        | cde     | No match |
|            | ade     | 1 match  |
|            | acdbea  | 3 matches (at acdbea) |

- `()` - Group

Parentheses () is used to group sub-patterns. For example, (a|b|c)xz match any string that matches either a or b or c followed by xz


| Expression   | String      | Matched?                          |
|--------------|-------------|-----------------------------------|
| (a\|b\|c)xz  | ab xz       | No match                          |
|              | abxz        | 1 match                           |
|              | axz cabxz   | 2 matches (at axz and cabxz)     |

