Makefile is a simple way to organize your code compilation
```makefile
hellomake: hellomake.c hellofunc.c
    gcc -o hellomake hellomake.c hellofunc.c -I.
```
Typing `make` with no arguments executes the first rule in the file. By putting the list of files on which the command depends on the first line after `:`, hellomake executes if any of those files change.
There must be a tab before any command in makefile.
```makefile
CC=gcc
CFLAGS=-I.

hellomake: hellomake.o hellofunc.o
    $(CC) -o hellomake hellomake.o hellofunc.o
```
We can define constants to tell `make` how we want to compile. The macro `CC` is the C compiler to use, and `CFLAGS` is the list of flags to pass to the compilation command. By putting the object files (`hellomake.o` and `hellofunc.o`) in the dependency list and in the rules, `make` knows it must first compile the `.c` versions individually, and then build the executable `hellomake`.
```makefile
CC=gcc
CFLAGS=-I.
DEPS = hellomake.h

%.o: %.c $(DEPS)
	$(CC) -c -o $@ $< $(CFLAGS)

hellomake: hellomake.o hellofunc.o
	$(CC) -o hellomake hellomake.o hellofunc.o
```
The macro `DEPS` is the set of `.h` files on which the `.c` files depend. The we define a rule that applies to all files ending in the `.o` suffix. The rule says that the `.o` file depends upon the `.c` version of the file and the `.h` files included in the `DEPS` macro. The rule then says that to generate `.o` files, `make` needs to compile the `.c` file using the compiler defined in `CC` macro. The `-c` flag says the generate the object file, the `-o $@` says to put the output of the compilation in the file named on the left side of the `:`. The `$<` is the first item in the dependencies list, and the `CFLAGS` macro is defined as above.
```makefile
CC=gcc
CFLAGS=-I.
DEPS = hellomake.h
OBJ = hellomake.o hellofunc.o

%.o: %.c $(DEPS)
	$(CC) -c -o $@ $< $(CFLAGS)

hellomake: $(OBJ)
	$(CC) -o $@ $^ $(CFLAGS)
```
The macros `$@` and `$^` means left and right side of the `:`, respectively. All object files should be listed as part of the macro `OBJ`. 