# FILESYSTEMS FUNCTIONS

---
| Function | Description | Input Example | Output |
| --- | --- | --- | --- |
| abspath | Returns the absolute path of a file or directory | `abspath("../path/to/file.txt")` | `"/absolute/path/to/file.txt"` |
| basename | Returns the base name component of a file path | `basename("/path/to/file.txt")` | `"file.txt"` |
| dirname | Returns the directory component of a file path | `dirname("/path/to/file.txt")` | `"/path/to"` |
| file | Reads the contents of a file on the local filesystem | `file("/path/to/file.txt")` | `"Hello, World!"` |
| filebase64 | Reads the contents of a file on the local filesystem and returns it as a base64-encoded string | `filebase64("/path/to/file.txt")` | `"SGVsbG8sIFdvcmxkIQ=="` |
| fileexists | Checks if a file exists on the local filesystem | `fileexists("/path/to/file.txt")` | `true` or `false` |
| fileset | Returns a list of file paths that match a pattern | `fileset(".", "*.txt")` | `["./file1.txt", "./file2.txt", ...]` |
| pathexpand | Expands a file path that contains `~` or `$HOME` to its full path | `pathexpand("~/file.txt")` | `"/home/user/file.txt"` |
| templatefile | Renders a template file with variables | `templatefile("template.tpl", { name = "Alice", age = 30 })` | `"Hello, Alice! You are 30 years old."` |
