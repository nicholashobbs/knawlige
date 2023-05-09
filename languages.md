# python

a shebang is a line at the top of a file that tells the operating system what program to use to run the file

```python
#!/usr/bin/env python3
```

make a byte string with b''



# assembly/c/c++

using gcc turns your file from file.c to file with no extension

c is the human version, the other file is the computer version

the stack has two registers - the rsp which is the stack pointer and the rbp which is the base pointer

push things on the stack and pop from the stack
stack grows up - so when you push an item, the pointer is decreased and when you pop an item, the pointer is increased

a word is 2 bytes or 64 bits

a dword is 4 bytes and a qword is 8 bytes

registers are another place to store values - there are only a limited amount of them, and they can only store a single value

registers are much faster to access- 100 or 1000 times faster than memory because they are on the cpu

instruction pointer or RIP - points to the next instruction to be executed

arguments are passed in registers - rdi, rsi, rdx, rcx, r8, r9 beyond that, they are passed on the stack

a flag is a particular bit of a register which can be on or off

instructions in assembly are called opcode

the first argument is the destination and the second argument is the source

mov is the move instruction

square brackets dereference a pointer - meaning go to the address that is stored in the pointer and get the value at that address

lea is the load effective address instruction - it loads the address of a variable into a register

lea rbi, [rbx+0x10] means load the address of rbx+0x10 into rbi

sub is the subtract instruction 
xor
and
or

push instruction grows the stack by 8 bytes 

jmp is the jump instruction goes to a specific address


# java/kotlin
# rust
# graphql

```graphql
query {
  comments {
    text
    author
  }
}
```

# javascript

```javascript
const cars = ["Saab", "Volvo", "BMW"]; // array

const person = {firstName:"John", lastName:"Doe", age:50, eyeColor:"blue"}; // object


```
