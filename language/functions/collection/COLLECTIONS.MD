# COLLECTIONS

---
| Function | Description | Input Example | Output |
| --- | --- | --- | --- |
| alltrue | Checks if all elements in a list are true | `alltrue([true, true, false])` | `false` |
| anytrue | Checks if any element in a list is true | `anytrue([false, true, false])` | `true` |
| chunklist | Breaks a list into smaller lists of a given size | `chunklist([1, 2, 3, 4, 5], 2)` | `[[1, 2], [3, 4], [5]]` |
| coalesce | Returns the first non-null value in a list of values | `coalesce(null, "Hello", null)` | `"Hello"` |
| coalescelist | Returns the first non-empty list in a list of lists | `coalescelist([], [], [1, 2, 3])` | `[1, 2, 3]` |
| compact | Removes any null or empty elements from a list | `compact(["Hello", null, "", "World"])` | `["Hello", "World"]` |
| concat | Concatenates two or more lists | `concat([1, 2], [3, 4])` | `[1, 2, 3, 4]` |
| contains | Checks if a list contains a given element | `contains([1, 2, 3], 2)` | `true` or `false` |
| distinct | Returns a new list containing only distinct elements from a given list | `distinct([1, 2, 3, 1, 2, 4])` | `[1, 2, 3, 4]` |
| element | Returns the element at a given index in a list | `element([1, 2, 3], 1)` | `2` |
| flatten | Flattens a list of lists into a single list | `flatten([[1, 2], [3, 4], [5]])` | `[1, 2, 3, 4, 5]` |
| index | Returns the index of the first occurrence of a given element in a list | `index([1, 2, 3], 2)` | `1` |
| keys | Returns a list of keys from a given map | `keys({a = 1, b = 2, c = 3})` | `["a", "b", "c"]` |
| length | Returns the length of a list or string | `length([1, 2, 3])` | `3` |
| list | Returns a new list containing the given arguments | `list(1, 2, 3)` | `[1, 2, 3]` |
| lookup | Returns the value associated with a given key in a map, or a default value if the key is not present | `lookup({a = 1, b = 2}, "b", 0)` | `2` |
| map | Transforms a list into a map | `map(["a", "b", "c"], [1, 2, 3])` | `{a = 1, b = 2, c = 3}` |
| matchkeys | Returns a map containing only the key-value pairs from the input map whose keys match the given pattern | `matchkeys({"a": 1, "b": 2, "c": 3}, "a")` | `{ "a": 1 }` |
| merge | Merges maps together, with later maps overriding earlier maps | `merge([{"a": 1}, {"b": 2}, {"a": 3}])` | `{ "a": 3, "b": 2 }` |
| one | Returns true if only one element in the given list is true | `one([true, false, false])` | `true` |
| range | Generates a sequence of numbers from start to end | `range(0, 5)` | `[0, 1, 2, 3, 4, 5]` |
| reverse | Returns a list with the elements in reverse order | `reverse([1, 2, 3])` | `[3, 2, 1]` |
| setintersection | Returns a set of the elements that appear in both sets | `setintersection([1, 2, 3], [2, 3, 4])` | `[2, 3]` |
| setproduct | Returns a set containing all possible combinations of the given sets | `setproduct([1, 2], ["a", "b"])` | `[[1, "a"], [1, "b"], [2, "a"], [2, "b"]]` |
| setsubtract | Returns a set of the elements that appear in the first set but not the second set | `setsubtract([1, 2, 3], [2, 3, 4])` | `[1]` |
| setunion | Returns a set of all unique elements from both sets | `setunion([1, 2, 3], [2, 3, 4])` | `[1, 2, 3, 4]` |
| slice | Returns a subset of a list based on a starting index and length | `slice([1, 2, 3, 4, 5], 2, 2)` | `[3, 4]` |
| sort | Returns a sorted list based on the given ordering function | `sort(["ab", "cd", "abc"], length)` | `["ab", "cd", "abc"]` |
| sum | Returns the sum of a list of numbers | `sum([1, 2, 3])` | `6` |
| transpose | Transposes a list of lists, turning rows into columns and vice versa | `transpose([[1, 2], [3, 4], [5, 6]])` | `[[1, 3, 5], [2, 4, 6]]` |
| values | Returns a list of all the values in a map | `values({"a": 1, "b": 2})` | `[1, 2]` |
| zipmap | Combines two lists into a map, using one as keys and the other as values | `zipmap(["a", "b"], [1, 2])` | `{ "a": 1, "b": 2 }` |


