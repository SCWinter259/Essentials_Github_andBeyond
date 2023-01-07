# Bash Commands on Linux

## Superuser and Software Management
- `pwd`: print working directory
- `cd [directory]`: change directory
- `ls`: list (the contents in current directory)
- `clear`: clear the terminal screen
- `sudo`: super user do, for higher authority commands in your machine
- `apt`: package management system (at least for Ubuntu)
  - `apt update`: download package information from all configured sources
  - `apt list [--installed/--upgradable/--all versions]`: display a list of packages that satisfy a certain criteria
  - `apt update`: install available updates
  - `apt search [regex]`: search for the given regex term(s) in the list of available packages
  - `apt install [package]`: install a particular package
  - `apt remove [package]`: remove a particular package
  - `apt autoremove`: remove the packages that were installed as dependencies to previously installed packages, and are no longer required by the system

## Files and Folders
- `touch [file name]`: create an empty file
- `mkdir [directory name]`: create an empty folder
- `cp [option] [destination]/[new name]`: copy a file to destination and changes name (if specified)
- `mv [option] [destination]/[new name]`: move a file to destination and changes name (if specified)
- `rm [file name]`: remove a file
- `rm -r [directory name]`: remove a directory (recursively)
- `rm *`: remove everything in current directory

## Text Editors
- `nano [file name]`: create file and enter nano
- `vim [file name]`: create file and enter vim

## Command Piping
- `|`: Pipe. Directs the output from the first command into the input for the second command
- `find [name]`: find a directory or a file
- `grep [-i/-R/-c] [words] [file name]`: searches a file for a particular pattern of characters and displays all lines that containn the pattern
  - `[-i]`: for case sensitive
  - `[-R]`: look in all files in current directory and subdirectories (in this case the file name can be omitted)
  - `[-c]`: count the number of times the pattern appears
- `[some results] >> [file name]`: appends information into a file or creates the file if it does not exist.
- `cat [file name]`: reads data from the file and gives its contents as output
- `echo [string]`: used to display line of string you entered
- `tail [number] [file name]`: writes the last number of lines in a file. Default is 10.
- `head [number] [file name]`: writes the first number of lines in a file. Default is 10.

## Getting Help
- `man`: manual
- `ls --help`

## Other Interesting Commands
- `date`: gives you the date