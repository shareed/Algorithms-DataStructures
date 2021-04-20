## Big O
##### Complexity
- measuring the rate that the time or memory requirements increase with as the number of inputs increases to an arbitrarily large number
- one algorithm that requires more time or memory to run with each new input is said to be more complex than another
- can be interpreted as the number of “steps” needed for it to complete
- this complexity is expressed in Big-O notation 
    - we express the algorithm as if it were a function named O
    - the complexity scale is given as some transformation of the variable N(the number of inputs to the algorithm)

**Big-O notation has no units, because the real-life runtime of an algorithm can be dependent on a lot of other factors – computer hardware quality, for example. If I have an O(n) algorithm running on a machine that takes minutes to complete, and I upgrade to faster hardware, the same algorithm might take seconds to complete – but it's still going to take a number of seconds that scales linearly to the number of inputs.**

###### Complexities for a best case, worst-case, and expected case scenario
- We are generally concerned with the worst-case measurement
- Best or expected cases can be used to compare two algorithms that have the same worst-case complexity

### Complexity vs Desirability
- using real numbers can confuse a comparison of algorithmic complexity with desirability
- a less complex algorithm might not always be desired, complexity does not mean more effcient
EXAMPLE:
1. You have a file that you are trying to send to your friend, who lives one hundred miles away. What’s the fastest way to do that? 
    1. You could use a file transfer service, like Dropbox
        - **Algorithm:** takes n amount of time, where n is the number of bytes in the file
        - For a consistent upload/download speed, a larger file will take longer to send to your friend, and the time scales linearly with the size of the file. But if we’re putting units on that measurement, or trying to determine which algorithm is more efficient, then the real download time might not be desirable. The complexity of the file transfer service is O(N), where N is the size of the file. If the file is so large that it takes hours to download, it might actually faster to take your hard drive and get in a car to physically deliver the hard drive to your friend. 
    2. Get in a car to physically deliver the hard drive to your friend
        - **Algorithm:** a two hour drive is faster and more efficient than a four hour download. The complexity of physically delivering the file is O(1) – it's always going to take 2 hours to drive to your friend directly. O(1) is less complex than O(N),so we must agree that driving is the least complex solution, even if it’s not the most efficient in all cases

**When you attach units to a measurement of algorithmic complexity, you can no longer compare algorithms directly without introducing other factors and complications. What if there's traffic? What if you get a faster internet connection?**

### Scaling factors 
- the lower the scaling factor of an algorithm, the less complex it is said to be,but remember when you try to tack units onto that measurement though, the system breaks

#### Algorithm that "runs in O(1) time"(constant-time)
- the least complex
**For example, let’s say you have a row of office supplies in front of you, and you are looking for the one pencil in the row. Your algorithm might be to start on the left side, and check each item sequentially to see if it's a pencil. In a best case scenario, your pencil would be the first item, and the number of items you have to check before finding your pencil would be the same. This is a constant-time algorithm, called O(1). If you could guarantee that the pencil was always the second item, it's still an O(1) algorithm – the amount of time required to find the pencil is constant, no matter how many items are in the row. The pencil is always the second item.** 




#### Algorithm that "tuns in O(log N)"(logarithmic)
- the number of steps the algorithm takes to complete will be close to the log-base-2 of the number of inputs(generally base-2)
**Example:** If we have 4 inputs, we take 2 iterations of our algorithm, between 5 and 8 inputs, we take 3 steps, etc
- divide and conquer(dividing inputs in half on each iteration)
**For example, you are trying to guess a number between 1 and 10 that your friend is thinking of.When you make a guess, your friend must tell you if his number is higher or lower than your guess. Being the clever person you are, you start by guessing 5 - right in the middle. Your friend tells you his number is lower. Now you can discard all the numbers greater than 5 and 5 itself. Your next guess is 2, and your friend says lower again - now you know his number must be 1! You were given 10 inputs, but you found the correct value in only 3 guesses, though it might have taken you 4. This is an example of a binary search, which runs in O(logN) time.**

#### Algorithm that "runs in O(n) time"(linear-time)
- worse than O(logN), but better than most other levels
- run time increases linearly with the number of inputs
- if one input requires 1ms, two inputs will require 2ms, 3 inputs 3ms, and so on
- in a worst-case scenario, you have to apply your algorithm to every single input before getting a desired result
**For example, let’s say you have a row of office supplies in front of you, and you are looking for the one pencil in the row. Your algorithm might be to start on the left side, and check each item sequentially to see if it's a pencil. But with no guarantees of pencil placement, then in a worst case scenario your pencil will be the last item in the row, meaning you’ll have to check every item. The number of items you have to check is equal to the number of inputs. This linear complexity, an O(n) algorithm**

#### Algorithm that "runs in O(N * log N)"(Quasilinear)
- is not commonly seen, outside of some optimized sorting algorithms
- check every input once, but complete an additional Log N number of operations for each of them

#### Algorithm that "runs in O(N^2)"(Polynomial) 
- it’s pretty bad
- an unoptimized algorithm, or an algorithm that has to iterate over the full range of inputs for each individual input

#### Algorithm that "runs in O(2^N)"(Exponential)
- usually shows up when you have a recursive algorithm that has to call itself twice each time it runs
- if it called itself three times instead, it would be O(3^N), and so on

#### Algorithm that "runs in O(N!)"(Factorial)
- is just about the worst possible complexity you can have
- usually represents a brute-force approach, you have to check every combination of every input against every other input
**There will almost always be an optimization to an N! algorithm, and if there’s not, there’s probably a better algorithm to use altogether.**
**Example:** A salesman needs to visit every town in an area exactly once. What path should he take to travel the shortest distance, but still visit every city at least once ? One way to solve this problem is to test every combination of distances between every city. 

- by comparing algorithms by the rate that they scale, you're comparing them as if they had an arbitrarily large number of inputs
- you can't really have an algorithm that scales at an O(N + 1) complexity
    - To use our previous pencil-finding example, what if every time you found your pencil, you had an extra step of having to write your name with it? If you only had 1 item in the row then having one more step doubles the work you have to do, but if you had 1 million items in the row, the amount of time it would take to write your name after searching for your pencil would be negligible.
- we can ignore smaller growth rates that use the same inputs
    - An algorithm that ran in O(N + LogN) time would just be O(N), for the same reason we drop constants. As the number of inputs increases, the additional impact of the lesser term approaches 0

#### What does that mean, “same inputs”? 
- consider an algorithm that takes two different sets of numbers as inputs. The algorithm:
    - searches the first set of numbers for the highest value: O(n)
    - then it sorts the second set of numbers: O(n^2)
    - then inserts the number from the first set into the second: O(n)
- the overall algorithm is not O(n + n^2 + n), because we are working on two different sets of numbers – two different and independent inputs
- scaling is very different if the first set of numbers is only one number and the second set is 1 million numbers, and vice versa
- In these cases, it's okay to say the algorithm is (a + b^2 + b). Which we can then reduce to O(a + b^2)
- because of scaling coefficients don't matter much either, an algorithm that scales at O(3n) is virtually indistinguishable from an O(n) algorithm for large numbers of inputs. O(n/2) is the same as O(1/2*n), and that coefficient can go too
- you can drop constants, drop coefficients, and drop all but the highest scaling factor for each type of input

**Big-O notation and complexity are at the heart of all algorithm and data structure discussion. These can be complicated topics, and there are entire college classes devoted to covering them. These are things a good programmer is expected to understand.**
___________________
- The act of creating variables, returning values, and checking conditions are all O(1) operations – they're just a single step or statement








