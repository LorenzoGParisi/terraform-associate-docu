# DATE TIME FUNCTIONS

---
| Function Name | Description | Example Input | Example Output |
| --- | --- | --- | --- |
| `formatdate` | Formats a timestamp into a string using a given format string. | `formatdate("YYYY/MM/DD", timestamp())` | `"2023/03/25"` |
| `timeadd` | Adds a duration to a given timestamp. | `timeadd("1h30m", timestamp())` | `"2023-03-25T01:30:00Z"` |
| `timecmp` | Compares two timestamps and returns 0 if they are equal, 1 if the first is later, and -1 if the first is earlier. | `timecmp(timestamp(), timestampadd("1h", timestamp()))` | `-1` |
| `timestamp` | Returns the current UTC time as a timestamp in ISO-8601 format. | `timestamp()` | `"2023-03-25T00:00:00Z"` (depending on the current UTC time) |
