# C Template

This a C template directory. It's purpose is to be used as a boilerplate for
various C projects.

It is a very minimal directory, with a Rakefile to compile the program via
command line.

---

## Testing and Globals

Included this **VERY** minimal C directory is a globals with a boolean and status
enumerable.

It also includes so RSpec sounding C testing helpers.

---

## Source Files

Place/find source files in the `src/*.c` directory.

Compiled object files can be found in `obj/*.o` directory.

---

## Header Files

Place/find header files in the `include/*.h` directory.

---

## Building

**Rakefile Usage:**
```
To Build/Rebuild:

$ rake

To Remove Object Files:

$ rake clean

To Remove Object Files and Executable:

$ rake clobber
```
