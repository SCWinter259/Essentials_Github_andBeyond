# Basics of Regex Syntax

## Basic character set

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

## Repeat count

- `{n}` indicates the number of times a character is repeated.
  - `be{2}r` is `beer`.
- `{n,}` means the character can be repeated `n+` times.
  - `be{3,}r` is `beeer`, `beeeer`, or more.
- `{n,m}` means the character can be repeated `n` to `m` times.
  - `be{1,3}` can be `ber`, `beer`, or `beeer`.

## Groups

- `()` can group expressions and `\n` can refer to group number.
  - `(ha)-\1,(haa)-\2` is `ha-ha,haa-haa`, where `\1` referes to the first group, `ha`, and `\2` refers to the second group, `haa`.
- `(?:)` is a non-capturing group.
  - `(?:ha)-ha,(haa)-\1` is still `ha-ha,haa-haa`, but `(haa)` is now group 1 because `(?:ha)` is non-capturing.

## Special characters

- `|` can be used like OR operation.
  - `(c|r)at|dog` can be `cat`, `rat`, or `dog`.
- `\` is an escape character.
  - `\*` can be used to find the `*` character without triggering anything.
- `^` finds things at the start of a line.
  - `^[0-9]` finds a number at the start of the line.
- `$` finds things at the end of a line.
  - `html$` finds the text `html` at the end of the line.
- `\w` finds letter, number, and underscore characters.
- `\W` finds anything that `\W` doesn't.
- `\d` finds numbers only (quite the same as `[0-9]`).
- `\D` finds only non-numeric characters.
- `\s` finds the space character.
- `\S` finds non-space character.

## Lookahead and lookbehind

- `(?=)` is a positive lookahead.
  - `\d+(?=PM)` only selects numerical values that have `PM` after them.
- `(!=)` is a negative lookahead.
  - `\d+(?!)` only selects numerical values that does not have `PM` after them.
- `(?<=)` is a positive lookbehind.
  - `(?<=\$)\d` only selects numerical values with `$` in front of it.
- `(?<!)` is a negative lookbehind.
  - `(?<!\$)\d` only selects numerical values without `$` in front of it.