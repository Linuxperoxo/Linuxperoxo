 .text
 .align 8
 .type _start,@function
 .globl _start
_start:
  movq $1,             %rax
  movq $1,             %rdi
  leaq _str(%rip),     %rsi
  movq _str_len(%rip), %rdx
  syscall

  movq $60,  %rax
  xorq %rdi, %rdi
  syscall

 .data
 .type _str,@object
_str:
  .ascii "O-------------------------------O\n"
  .ascii "| Hello there! :^)              |\n"
  .ascii "| Im 18 years old               |\n"
  .ascii "| And I Love Zig, C/C++ and ASM |\n"
  .asciz "O-------------------------------O\n"

 .align 8
 .type _str_len,@object
_str_len:
  .quad (. - .str)
