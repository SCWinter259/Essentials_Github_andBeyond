# How to write Bash Scripts

A shell script ends with `.sh` (like `test.sh`)

First thing to do is to type in your interpreter

```bash
#!/usr/bin/bash
# I am a comment
STRING="Hello World"
echo $STRING    # use the dollar sign for calling variable
```

To run, type `./[file name]`

Just in case your file does not have permisson to be ran on the terminal, you can type `chmod +x [file name]`

## Programmable stuff

You can have functions and local variables

```bash
#!/usr/bin/bash
STRING="Hello World"
echo $STRING
function bash {
    local STRING="Local Hello"
    echo $STRING
}

bash    # type out the name to run the function
```

You can take in arguments

```bash
for arg1 in "$@"    # $@ represents the whole line of argument
do
echo $arg1
done
```

Conditional statements:

```bash
if [ expression1 ]
then
   statement1
   statement2
   .
   .
elif [ expression2 ]
then
   statement3
   statement4
   .
   .
else
   statement5
fi
```

## read

The syntax for bash `read` command is `read <options> <arguments>`
- `-a <array>`: Assigns the provided word sequence to a variable named `<array>`
- `-d <delimeter>`: Reads a line until the provided `<delimeter>` instead of a new line.
- `-p <prompt>`: Outputs the prompt string before reading user input
- `-s`: Does not echo the user's input
- `-u <file descriptor>`: Read from file descriptor instead of standard input.

## Operators

You can compare strings in bash
- `[[string1 == string2]]` or `[string1 = string2]`: True if the two strings are equal

```bash
#!/bin/bash

read -p "Enter first string: " VAR1
read -p "Enter second string: " VAR2

if [[ "$VAR1" == "$VAR2" ]]; then
    echo "Strings are equal."
else
    echo "Strings are not equal."
fi
```

- `string1 != string2`: True if the two strings are unequal
- `string1 > string2`: True if the left string is greater than the right string sorted by lexicographical (alphabetical) order.
- `string1 < string2`: True if the left string is smaller than the right string sorted by lexicographical (alphabetical) order.
- `-z string`: True if the string length is zero
- `-n string`: True if the string length is non-zero

You can also use logical `&&` and `||`:

```bash
[[ "string1" == "string2" ]] && echo "Equal" || echo "Not equal"
```