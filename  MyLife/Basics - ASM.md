
Before we need to understand basics on how the Cpu works


With the registers explained in [[Basics - Cpu]], we can do some operations like moving:

```nasm
mov rdi, 8 
```

moves the number 8 the constant value into the register rdi.

```nasm
mov rdi, rsi
```

move into rdi the value rsi.

Also important are Memory-Operations
```nasm
move rdi
```
this is called a qword pointer of rsi, that means read the value of rsi