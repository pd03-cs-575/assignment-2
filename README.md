# CS 575 Assignment 2

This assignment is an introduction to OS system calls.

## `strace` table

| System calls  |  C  |  C++  |  Java  |  Python  |  Bash  |
|---|---|---|---|---|---|
|  `execve()`  | 1  |  1  |  1  | 1  |  1  |
|  `open()` / `openat()`  |  2  |  5  |  21  |  33  |  20  |
|  `close()`  |  2  |  5  |  10  |  28  |  7  |
|  `read()`  |  1  |  4  |  9  |  34  |  5  |
|  `write()`  |  1  |  1  |  0  |  1  |  1  |
|  `mmap()` |  7  |  18  |  29  |  24  |  12  |