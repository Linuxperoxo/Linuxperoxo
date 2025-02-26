.section .text
.align 16
.type .main, @function
.global main
main:
  movq $1, %rax
  movq $1, %rdi
  leaq .str(%rip), %rsi
  movq .str_len(%rip), %rdx
  syscall

  movq $60, %rax
  xorq %rdi, %rdi
  syscall

.section .rodata
.align 16
.type .str, @object
.str:
  .ascii "O--------------------------O\n"
  .ascii "| Hello there! :^)         |\n"
  .ascii "| Im 17 years old          |\n"
  .ascii "| And I Love C/C++ and ASM |\n"
  .asciz "O--------------------------O\n"

.type .str_len, @object
.str_len:
  .quad (. - .str)

.section .note.GNU-stack
