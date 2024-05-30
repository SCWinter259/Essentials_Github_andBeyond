# Basics of Regex Syntax

- Type a word to get the exact match.
- `[-]` for a range.
  - `[a-z]` for characters in the range of a-z, and `b[6-9]` will match `b6`, `b7`, `b8`, or `b9`.
- `[^]` excludes characters.
  - `b[^ea]ar` cannot be `bear` or `baar`.
- `*` means a character can occur zero, one or more times.
  - `be*r` can be `br`, `ber`, `beer`, and so on.
- `+` means a character can occur once or more times.
  - `be+r` can be `ber`, `beer`, `beeer`, and so on.
- `?` means a character is optional.
  - `colou?r` can be `color` or `colour`.