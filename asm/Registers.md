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

Now if you were to print rax or inspect rax in a debugger, you can see the result
of that addition in the rax register: **30**

_Side Note: if you want to inspect a value in gdb, type `p/d $rax` (for the 
above) and it'll show you the value of rax in decimal form._

### Sizes of Registers:

As seen above in the table, there are different names for the same registers 
depending on their size. `RAX` for example is a 64 bit register. `EAX` is the same
register, but only the lower 32 bits of RAX. And so on for `AX` and `AL` and `AH`.

The reason these registers subdivide into smaller sizes is to maintain backwards
compatibility. In the early days of computing, there weren't CPUs with 64 bit registers.
They had 8 bit CPUs, or 16 bit CPUs. Rather than redoing thousands of lines of code
and breaking compatibility for older devices that are still in use, larger bit registers
were built ontop of the smaller registers.

As for the sizes themselves, we can visualize `EAX` as being the lower half of `RAX`
and `AX` being the lower half of `EAX`. What is unique is that `AX` subdivides into
`AL` **and** `AH` (A lower, A Higher) - we can use both the lower 8 bits and upper 8
bits.

This naming conventions apply to a lot of the registers listed above in the table. 

<img src=https://diveintosystems.org/book/C7-x86_64/_images/register.png width=500>

### Reserved Registers

There are some registers that are reserved for certain things