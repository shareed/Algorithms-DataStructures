# MEMORY
**A computer's memory is broken up into bytes – 8 bits, or binary digits 8 bits makes a byte, 1024 bytes makes a kilobyte, 1024 kilobytes makes a megabyte, etc.**
- Computer programs use variables(reserved memory space used to store values) in the same way a math equation does – they're a store for a value of some kind, but the particular value can be changed
- Some languages separate those values into groups, like integers, alphanumeric characters, or decimal numbers. This is called typing.
- Variables, typed or untyped, are given a fixed amount of memory space that it is allowed to occupy

**For example, in Java, an integer variable is allowed 4 bytes – 32 bits – of memory. This has two effects: first, the range of integer values that variable could store is limited to what can be expressed with 32 binary digits; second, the amount of memory reserved is always going to be 4 bytes, even if the actual value stored doesn't require that much space.** 
- Every byte of memory has an address, which is where the computer knows to look for a particular value
- If a variable occupies more than one byte, typically the computer will know to access the variable through the address of the first byte reserved
- If any other variables are created, the computer knows to reserve memory after the initial address plus the number of bytes reserved for the variable stored there
______________________________________