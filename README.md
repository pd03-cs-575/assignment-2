# CS 575 Assignment 2

This assignment is an introduction to OS system calls.

## Question 1 & 2

The files related to these programs are included in this directory.

## Question 3

See below for table results.

### `strace` table

| System calls  |  C  |  C++  |  Java  |  Python  |  Bash  |
|---|---|---|---|---|---|
|  `execve()`  | 1  |  1  |  1  | 1  |  1  |
|  `open()` / `openat()`  |  2  |  5  |  21  |  33  |  20  |
|  `close()`  |  2  |  5  |  10  |  28  |  7  |
|  `read()`  |  1  |  4  |  9  |  34  |  5  |
|  `write()`  |  1  |  1  |  0  |  1  |  1  |
|  `mmap()` |  7  |  18  |  29  |  24  |  12  |

### `strace -e` file size table

Found using `ls -ltrh` command, displayed in bytes.

|  C  |  C++  |  Java  |  Python  |  Bash  |
|---|---|---|---|---|
| 1.2k  |  3.0k  |  6.5k  |  9.0k  |  4.0k  |

## Question 4

Although all programs have the same functionality of printing "hello world" to standard output, we can see from the tables above that each program performs different number of system calls. These programs are ran on the same virtual machine, so we assume variable `z` CPU clock rate is similar when executing these programs

A possible conclusion, then, that some program runs slower or faster because some languages perform more system calls `x` than others.
 
From the table, we see that C performs the least number of system calls. The program only requires 2 opens, 2 closes, 1 read, 1 write, and 7 memory mappings. Meanwhile, C++` has slightly more calls. Python and Java has significantly more system calls, presumably from loading more libraries and dependencies. Bash is somewhere in between with the number of system calls.

The `strace` file sizes also supports the same conclusion. Therefore, we can assume that CPU time for each program is sorted in ascending order as: C -> C++ -> bash -> Java -> Python.
