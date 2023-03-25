# STRING FUNCTIONS

---
| Function | Description | Input Example | Output |
| --- | --- | --- | --- |
| chomp | Removes any trailing newline characters from a string | `chomp("Hello\n")` | `"Hello"` |
| endswith | Checks if a string ends with a given suffix | `endswith("Hello, World!", ", World!")` | `true` or `false` |
| format | Formats a string with placeholders | `format("Hello, %s!", "World")` | `"Hello, World!"` |
| formatlist | Formats a list of strings with a given format string | `formatlist("Hello, %s!", ["Alice", "Bob", "Charlie"])` | `["Hello, Alice!", "Hello, Bob!", "Hello, Charlie!"]` |
| indent | Indents each line of a string by a given number of spaces | `indent("Hello\nWorld", 2)` | `"  Hello\n  World"` |
| join | Joins a list of strings with a separator string | `join(", ", ["Alice", "Bob", "Charlie"])` | `"Alice, Bob, Charlie"` |
| lower | Converts a string to lowercase | `lower("Hello, World!")` | `"hello, world!"` |
| regex | Searches a string for a regular expression pattern and returns the first match | `regex("Hello, (\\w+)!", "Hello, World!")` | `"World"` |
| regexall | Searches a string for a regular expression pattern and returns all matches | `regexall("(\\w+)", "Hello, World!")` | `["Hello", "World"]` |
| replace | Replaces all occurrences of a substring in a string with another string | `replace("Hello, World!", "Hello", "Hi")` | `"Hi, World!"` |
| split | Splits a string into a list of substrings using a delimiter | `split(", ", "Alice, Bob, Charlie")` | `["Alice", "Bob", "Charlie"]` |
| startswith | Checks if a string starts with a given prefix | `startswith("Hello, World!", "Hello")` | `true` or `false` |
| strrev | Reverses the characters in a string | `strrev("Hello, World!")` | `"!dlroW ,olleH"` |
| substr | Returns a substring of a string | `substr("Hello, World!", 0, 5)` | `"Hello"` |
| title | Converts a string to title case | `title("hello, world!")` | `"Hello, World!"` |
| trim | Removes any leading or trailing whitespace from a string | `trim("  Hello, World!  ")` | `"Hello, World!"` |
| trimprefix | Removes a given prefix from the beginning of a string | `trimprefix("Hello, World!", "Hello, ")` | `"World!"` |
| trimsuffix | Removes a given suffix from the end of a string | `trimsuffix("Hello, World!", ", World!")` | `"Hello"` |
| trimspace | Removes any leading or trailing whitespace from a string and collapses any internal whitespace to a single space character | `trimspace("  Hello,  World!  ")` | `"Hello, World!"` |
| upper | Converts a string to uppercase | `upper("Hello, World!")` | `"HELLO, WORLD!"` |
