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
