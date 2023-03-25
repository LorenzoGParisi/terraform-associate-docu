# HASH AND CRYPTOS FUNCTIONS

---
| Function Name | Description | Input Example | Output Example |
| --- | --- | --- | --- |
| `bcrypt` | Generate a bcrypt password hash | `bcrypt("myPassword", 8)` | `$2a$08$yKLYs2sKsWGwoG6ayWcPr.QiK6U45L6LOdKGmOWgT6Tk7qwMN4l4u` |
| `filebase64sha256` | Generate SHA256 digest of a file and return its base64 encoded string | `filebase64sha256("/path/to/file")` | `xLf1Rt...` |
| `filebase64sha512` | Generate SHA512 digest of a file and return its base64 encoded string | `filebase64sha512("/path/to/file")` | `X22y51...` |
| `filemd5` | Generate MD5 digest of a file and return its hexadecimal encoded string | `filemd5("/path/to/file")` | `e1d9f8...` |
| `filesha1` | Generate SHA1 digest of a file and return its hexadecimal encoded string | `filesha1("/path/to/file")` | `da39a3...` |
| `filesha256` | Generate SHA256 digest of a file and return its hexadecimal encoded string | `filesha256("/path/to/file")` | `3a3e32...` |
| `filesha512` | Generate SHA512 digest of a file and return its hexadecimal encoded string | `filesha512("/path/to/file")` | `ba4be4...` |
| `md5` | Generate MD5 digest of a string and return its hexadecimal encoded string | `md5("myPassword")` | `6d833a...` |
| `rsadecrypt` | Decrypt data using an RSA private key | `rsadecrypt(open("/path/to/key", "r").read(), base64decode("..."))` | `mySensitiveData` |
| `sha1` | Generate SHA1 digest of a string and return its hexadecimal encoded string | `sha1("myPassword")` | `2fd4e1...` |
| `sha256` | Generate SHA256 digest of a string and return its hexadecimal encoded string | `sha256("myPassword")` | `8d969e...` |
| `sha512` | Generate SHA512 digest of a string and return its hexadecimal encoded string | `sha512("myPassword")` | `deeb07...` |
| `uuid` | Generate a random UUID | `uuid()` | `4f2e319f-c7...` |
| `uuidv5` | Generate a UUID version 5 (SHA-1 hash of a namespace and a name) | `uuidv5("6ba7b811-9dad-11d1-80b4-00c04fd430c8", "myNamespace")` | `da49e6e1-...` |
