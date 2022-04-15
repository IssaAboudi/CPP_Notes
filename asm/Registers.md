#What are Registers in Assembly

Registers are a little intimidating when you first start coding in Assembly.
They pretty much hold whatever you want them to hold, and they have weird 
naming patterns that correlate with their sizes.

## Registers in x86
<img src="https://i.imgur.com/e7j0c5E.png" width="500"/>

## What do we do with registers?
Registers are used to store and interact with values. For example, if you
want to add numbers, you can do so by using registers and performing operations

```asm
mov rax, 5 ; copy 5 to rax register
mov rbx, 25 ; copy 25 to rbx register
add rax, rbx ; add values in rax and rbx together and store in rax
```

Now if you were to print rax or inspect rax in a debugger, you can see 