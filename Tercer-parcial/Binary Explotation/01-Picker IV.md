# Picker IV

## Descripción

Can you figure out how this program works to get the flag?Connect to the program with netcat:`$ nc saturn.picoctf.net 51934`The program's source code can be downloaded [here](https://artifacts.picoctf.net/c/527/picker-IV.c). The binary can be downloaded [here](https://artifacts.picoctf.net/c/527/picker-IV).

## Pistas

1.- With Python, there are no binaries. With compiled languages like C, there is source code, and there are binaries. Binaries are created from source code, they are a conversion from the human-readable source code, to the highly efficient machine language, in this case: x86_64.

2.- How can you find the address that `win` is at?

## Solución

```
┌──(kali㉿kali)-[~/picoctf/b_exploitation/PickerIV]
└─$ cat picker-IV.c
#include <stdio.h>
#include <stdlib.h>
#include <signal.h>
#include <unistd.h>

void print_segf_message(){
  printf("Segfault triggered! Exiting.\n");
  sleep(15);
  exit(SIGSEGV);
}

int win() {
  FILE *fptr;
  char c;

  printf("You won!\n");
  // Open file
  fptr = fopen("flag.txt", "r");
  if (fptr == NULL)
  {
      printf("Cannot open file.\n");
      exit(0);
  }

  // Read contents from file
  c = fgetc(fptr);
  while (c != EOF)
  {
      printf ("%c", c);
      c = fgetc(fptr);
  }

  printf("\n");
  fclose(fptr);
}

int main() {
  signal(SIGSEGV, print_segf_message);
  setvbuf(stdout, NULL, _IONBF, 0); // _IONBF = Unbuffered

  unsigned int val;
  printf("Enter the address in hex to jump to, excluding '0x': ");
  scanf("%x", &val);
  printf("You input 0x%x\n", val);

  void (*foo)(void) = (void (*)())val;
  foo();
}
                                                                                                                      
┌──(kali㉿kali)-[~/picoctf/b_exploitation/PickerIV]
└─$ chmod +x picker-IV
                                                                                                                      
┌──(kali㉿kali)-[~/picoctf/b_exploitation/PickerIV]
└─$ gdb picker-IV -q
Reading symbols from picker-IV...
(No debugging symbols found in picker-IV)
(gdb) disassemble win
Dump of assembler code for function win:
   0x000000000040129e <+0>:     endbr64
   0x00000000004012a2 <+4>:     push   %rbp
   0x00000000004012a3 <+5>:     mov    %rsp,%rbp
   0x00000000004012a6 <+8>:     sub    $0x10,%rsp
   0x00000000004012aa <+12>:    lea    0xd74(%rip),%rdi        # 0x402025
   0x00000000004012b1 <+19>:    call   0x4010f0 <puts@plt>
   0x00000000004012b6 <+24>:    lea    0xd71(%rip),%rsi        # 0x40202e
   0x00000000004012bd <+31>:    lea    0xd6c(%rip),%rdi        # 0x402030
   0x00000000004012c4 <+38>:    call   0x401150 <fopen@plt>
   0x00000000004012c9 <+43>:    mov    %rax,-0x10(%rbp)
   0x00000000004012cd <+47>:    cmpq   $0x0,-0x10(%rbp)
   0x00000000004012d2 <+52>:    jne    0x4012ea <win+76>
   0x00000000004012d4 <+54>:    lea    0xd5e(%rip),%rdi        # 0x402039
   0x00000000004012db <+61>:    call   0x4010f0 <puts@plt>
   0x00000000004012e0 <+66>:    mov    $0x0,%edi
   0x00000000004012e5 <+71>:    call   0x401170 <exit@plt>
   0x00000000004012ea <+76>:    mov    -0x10(%rbp),%rax
   0x00000000004012ee <+80>:    mov    %rax,%rdi
   0x00000000004012f1 <+83>:    call   0x401120 <fgetc@plt>
   0x00000000004012f6 <+88>:    mov    %al,-0x1(%rbp)
   0x00000000004012f9 <+91>:    jmp    0x401315 <win+119>
   0x00000000004012fb <+93>:    movsbl -0x1(%rbp),%eax
   0x00000000004012ff <+97>:    mov    %eax,%edi
   0x0000000000401301 <+99>:    call   0x4010e0 <putchar@plt>
   0x0000000000401306 <+104>:   mov    -0x10(%rbp),%rax
   0x000000000040130a <+108>:   mov    %rax,%rdi
   0x000000000040130d <+111>:   call   0x401120 <fgetc@plt>
   0x0000000000401312 <+116>:   mov    %al,-0x1(%rbp)
   0x0000000000401315 <+119>:   cmpb   $0xff,-0x1(%rbp)
--Type <RET> for more, q to quit, c to continue without paging--
   0x0000000000401319 <+123>:   jne    0x4012fb <win+93>
   0x000000000040131b <+125>:   mov    $0xa,%edi
   0x0000000000401320 <+130>:   call   0x4010e0 <putchar@plt>
   0x0000000000401325 <+135>:   mov    -0x10(%rbp),%rax
   0x0000000000401329 <+139>:   mov    %rax,%rdi
   0x000000000040132c <+142>:   call   0x401100 <fclose@plt>
   0x0000000000401331 <+147>:   nop
   0x0000000000401332 <+148>:   leave
   0x0000000000401333 <+149>:   ret
End of assembler dump.
(gdb) quit
                                                                                                                      
┌──(kali㉿kali)-[~/picoctf/b_exploitation/PickerIV]
└─$ nc saturn.picoctf.net 59764
Enter the address in hex to jump to, excluding '0x': 40129e
You input 0x40129e
You won!
picoCTF{n3v3r_jump_t0_u53r_5uppl13d_4ddr35535_b8de1af4}
```

## Bandera

picoCTF{n3v3r_jump_t0_u53r_5uppl13d_4ddr35535_b8de1af4}

## Notas adicionales



## Referencias
- https://artifacts.picoctf.net/c/527/picker-IV.c
- https://artifacts.picoctf.net/c/527/picker-IV