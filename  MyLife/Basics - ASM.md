
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
move rdi, qword ptr [rsi]
```
this is called a qword pointer of rsi, that means treat the value in rsi as a pointer and then remove the qword length thats 8 bytes and put it into rdi

We can also do this in reverse:

```nasm
mov qword ptr [rsi], rdi
```


Move to the qword ptr in rsi, the value in rdi


First one was, we took values from memoy and put it into registers, now we took values that are in registers into memoy, thats a store operation.