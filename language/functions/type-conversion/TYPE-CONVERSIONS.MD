# TYPE CONVERSION FUNCTIONS

---
| Function     | Description                                                                           | Input Example                | Output Example         |
| ------------ | ------------------------------------------------------------------------------------- | ---------------------------- | ---------------------- |
| `can`        | Converts the given value to a bool indicating whether it can be used as a Terraform expression. | `"true"` | `true` |
| `nonsensitive` | Wraps a value so it is never printed in plain text to logs or the console.           | `"my-secret"` | `SENSITIVE` |
| `sensitive`  | Marks the given value as sensitive, so it will not be shown in plain text in logs or the console. | `"my-secret"` | `SENSITIVE` |
| `tobool`     | Converts the given value to a bool.                                                   | `"true"`                     | `true`                 |
| `tolist`     | Converts the given value to a list.                                                   | `"foo"`                      | `["foo"]`              |
| `tomap`      | Converts the given value to a map.                                                    | `{"foo": "bar"}`            | `{foo = "bar"}`       |
| `tonumber`   | Converts the given value to a number.                                                 | `"42"`                       | `42`                   |
| `toset`      | Converts the given value to a set.                                                    | `["foo", "bar"]`            | `["foo", "bar"]`       |
| `tostring`   | Converts the given value to a string.                                                 | `42`                         | `"42"`                |
| `try`        | Attempts to convert the given value to the desired type, returning the default value if unsuccessful. | `"true"` | `true` or `default_value` |
| `type`       | Returns the type of the given value.                                                  | `42`                         | `"number"`             |
