# ENCODING FUNCTIONS

---
| Function | Description | Input Example | Output |
| --- | --- | --- | --- |
| base64decode | Decodes a base64-encoded string | `base64decode("SGVsbG8gV29ybGQh")` | `"Hello World!"` |
| base64encode | Encodes a string as base64 | `base64encode("Hello World!")` | `"SGVsbG8gV29ybGQh"` |
| jsondecode | Decodes a JSON-encoded string into a map or list | `jsondecode("{\"name\": \"Alice\", \"age\": 30}")` | `{name = "Alice", age = 30}` |
| jsonencode | Encodes a map or list as a JSON-encoded string | `jsonencode({name = "Alice", age = 30})` | `"{"name":"Alice","age":30}"` |
| urlencode | Encodes a string as a URL-encoded string | `urlencode("Hello World!")` | `"Hello%20World%21"` |
