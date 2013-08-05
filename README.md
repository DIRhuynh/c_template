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

---

## Example Testing Driver

**main.c**

```
#include "globals.h"
#include "challenge.h"

status test_is_prime()
{
  int a = 0, b = 1, c = 2, d = 4, e = 29;
  status test_result;

  printf("\n--------------------------------------------------\n\n");
  printf("Testing is_prime():\n");

  test_result = expect_false(is_prime(a), "0 is not a prime");

  if (test_result == SUCCESS) {
    test_result = expect_false(is_prime(b), "1 is not a prime");
  }

  if (test_result == SUCCESS) {
    test_result = expect_true(is_prime(c), "2 is a prime");
  }

  if (test_result == SUCCESS) {
    test_result = expect_false(is_prime(d), "4 is not a prime");
  }

  if (test_result == SUCCESS) {
    expect_true(is_prime(e), "29 is not a prime");
  }

  printf("\n\n--------------------------------------------------\n");
  return SUCCESS;
}

int main(int argc, char* argv[])
{
  test_is_prime();
  return 0;
}
```

### Output

```
$ ./challenge.osx

--------------------------------------------------

Testing is_prime():
0 is not a prime: passed.
1 is not a prime: passed.
2 is a prime: failed
  expected TRUE(1), got FALSE(0).


--------------------------------------------------
```
