# libmacho
an assembly library for coding in Mach-O Assembly.

# Syscalls
| Syscall        | Parameter 1 (rdx)         | Parameter 2 (rdi)        | Parameter 3 (rsi) | Parameter 4 (rax) |
|----------------|---------------------------|--------------------------|-------------------|-------------------|
| SYSCALL_EXIT   | None                      | Error code               | None              | None              |
| SYSCALL_WRITE  | Size of string            | File descriptor/1=STDOUT | String            | None              |
| SYSCALL_INPUT  | Maximum amount of letters | None                     | Input string      | None              |
| SYSCALL_FOPEN  | 0x1B6                     | Filename                 | Flags             | None              |
| SYSCALL_FCLOSE | None                      | File descriptor          | None              | None              |

# Flags
| Flag        | Purpose                                                                       |
|-------------|-------------------------------------------------------------------------------|
| O_CREAT     | Creates a file if it doesn't exist.                                           |
| O_RDONLY    | Sets file to read only.                                                       |
| O_WRONLY    | Sets file to write only.                                                      |
| O_RDWR      | Sets file to read/write.                                                      |
| O_TRUNC     | Truncates file to zero length.                                                |
| O_NOCTTY    | If filename is TTY/terminal, this flag makes sure it isn't the main terminal. |
| O_DIRECTORY | File is directory.                                                            |
| O_APPEND    | Appends to file.                                                              |
| O_NOFOLLOW  | Don't follow symlinks.                                                        |
| O_CLOEXEC   | Closes automatically after write.                                             |
| O_EXCL      | When used with O_CREAT, errors if file exists.                                |
Any others were too hard to explain in simple terms.

# How to:
## Install
Simply drag into your dev folder, and add it to the toolchain you're using, example: `nasm -o asmacho main.s` -> `nasm -o asmacho libmacho.s main.s`
## Use
Just set up the parameters (in the table above) how you like em, then call them, example program with `SYSCALL_WRITE` writing to STDOUT:
```
text db "Hello!"
mov rdx, 6
mov rdi, 0x1
mov rsi, text
call SYSCALL_WRITE
call SYSCALL_EXIT
```
