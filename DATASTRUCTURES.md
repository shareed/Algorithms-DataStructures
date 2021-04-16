## Data Structures
**The different ways of organizing data in programs are called data structures**
_________________________

### Arrays
- a series of reserved memory spaces for a fixed number of variables
- an array of 5 integers, and each integer is reserved 4 bytes of memory, my array is a chain of 20 reserved bytes of memory

#### Array Indices
- I can place values into this array at any point using an index
- Array indices are always wrapped by brackets and start at 0, and go up to the array's size, minus one

#### Accessing and Changing Value
- under the hood, an array is accessed by the first memory address reserved for the first index
- accessing the value in another index is simply a matter of accessing the address at…the array's first address, plus the desired index multiplied by the number of bytes reserved for each variable
    - So if my array starts at address 2, and each integer is reserved 4 bytes, then accessing array index 3 is as simple as accessing memory address 2 + (4 * 3), or memory address 14
- Array values are  memory adjacent, which makes accessing the values of an array just about as fast as anything can possibly be
- finding the value stored in any index of an array simply requires a single multiplication equation, we say that an accessing an array by index is done in O(1) time. No matter how big the array is, accessing the value at any index only requires one step. This also holds true for changing the value at any index

#### Array size
- by reserving blocks of adjacent memory at once when the array is created, an array's size is fixed
- to increase the size of an array you will have to create an entirely new array of adjacent reserved bytes, and copy the values of the first array into the second
- if our array reserves 4 bytes of memory in a row, and another variable should occupy the 5th, our array can't expand smoothly. So expanding our array requires creating a new array – reserving memory is always an O(1) task, as is deleting the old array once everything is copied over
- copying each value will require iterating over the entire length of the old array, which is an O(n) task. So for an O(1 + N + 1) algorithm, remember that we can just say it's an O(N) task
- This also illustrates why it's better to create an array of a size you know you need, rather than start small and expand later
____________________________


### Strings
- a series of alphanumeric characters, like a word or a sentence
- implemented as arrays of characters(in most lang), where each character is allowed a certain number of bytes for its encoding
### Algorithm Example:
** Algorithm that determines if a given String is a palindrome. A palindrome is a series of characters that are the same when read forward or backward, like “racecar”. Generally, you ignore spaces with palindromes, but for simplicity we'll assume our input phrase has no spaces or special characters.** 

##### Pseudo Code
**Actions**
1. input: String phrase
2. output: boolean(true/false) result

**Data**
1. variable length = phrase.length --> O(1)
2. counter variable c to hold the index of the phrase = 0 --> O(1)

**Functionality**
1. loop to iterate over each character in the input phrase, we only need to iterate over half the characters in the phrase string to determine if the phrase is a palindrome. So we use a while-loop, while the value of c is less than or equal to half the length of the input phrase the loop will continue to run
    - `while (c <= length/2>)` --> O(n/2)
2. Compare the first character to the last character, the second character to the second-from-last character, etc.
    - `if(phrase[c] != phrase[length - 1 - c])`
    ```
        while (c <= length/2>)
            if(phrase[c] != phrase[length - 1 - c]) --> O(1)
            return false --> O(1)
            c = c + 1 --> O(1)
        return true// --> O(1)
    
    ```
    - “c” increments by 1 with each loop iteration, the characters compared converge toward the center of the input phrase
    - When we compare the two characters, if they're not equal then we know the phrase cannot be a palindrome, and we return false
    - If the word is a palindrome and the loop will exit when “c” is greater than half the length of the phrase.When the loop exits this way, the word must be a palindrome, and so the value “true” is returned
    
- The act of creating variables, returning values, and checking conditions are all O(1) operations – they're just a single step or statement
- Each iteration of a loop can also be said to be O(1). But our loop iterates over characters in the input phrase, and the longer the input phrase is, the more loop iterations our algorithm will have. At first glance, we could try saying this algorithm is O(1 + 1 + n/2 + 1), where n is the number of characters in the input phrase.But we know that we discard coefficients and smaller scaling factors, so this algorithm is really just O(n)
**These are just a few of the basic data structures you'll need to be able to work with to develop your own algorithms.In fact, arrays form the backbone to most other data structures, and are mandatory to understanding them**