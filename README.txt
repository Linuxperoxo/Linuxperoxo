/==================================================================================================O
|                                                                                                  |
| #include <unistd.h>                                                                              |
| #include <string.h>                                                                              |
|                                                                                                  |
| #define MSG "Hello there! :^)\n Im 17 years old\n And I Love C/C++ and ASM\n"                    |
|                                                                                                  |
| int main(int argc, char** argv){                                                                 |
|    write(STDOUT_FILENO, MSG, strlen(MSG));                                                       |
|    return 0;                                                                                     |
| }                                                                                                |
|                                                                                                  |
O==================================================================================================/

/==================================================================================================O
|                                                                                                  |
| section .data                                                                                    |
|  __msg db "Hello there! :^)", 0x0A, "Im 17 years old", 0x0A, "And I Love C/C++ and ASM", 0x0A    |
|  __msg_len equ 58                                                                                |
|                                                                                                  |
| section .text                                                                                    |
|   global _start                                                                                  |
|                                                                                                  |
| _start:                                                                                          |
| mov rax, 1                                                                                       |
| mov rdi, 1                                                                                       |
| mov rsi, __msg                                                                                   |
| mov rdx, __msg_len                                                                               |
| syscall                                                                                          |
|                                                                                                  |
| mov rax, 60                                                                                      |
| xor rdi, rdi                                                                                     |
| syscall                                                                                          |
|                                                                                                  |
O==================================================================================================/
