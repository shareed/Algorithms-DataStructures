## Stack
- similar to lists, but they have rules about the order in which you can access their contents
- These rules make them useful for emulating real-life constructs
- stack is a data structure that works on a Last In First Out principle, or LIFO
- best used when you need to enforce an ordering for your data or processing
- pushing: add/push item to the top of the stack
- popping: remove/pop an item off the top of the stack
- cannot insert an item to or remove one from anywhere else in the stack but the top
- you can peek at the item at the top of the stack – this returns its data without removing the item itself 
- the only real difference between a stack and a queue is that stacks are Last In First Out, while queues are First In First Out
- removing or peeking from a queue should return the oldest element, while popping or peeking from a stack should return the newest.
_____________

**Some languages offer a pre-built implementation for stacks, but not all of them do. For those that don’t, you should recognize their similarity to single-linked lists**
- Pushing a new item is the same as adding a new node as the head, and setting the “next” property to the old head
- Popping is the same as removing the node that operated as the old head

### Complexity
- constant-time inserts and deletes

____________________
**Program execution is handled by a stack. When a new function is invoked, that invocation is pushed to the top of the stack. When the computer begins execution again, that new invocation is peeked, and popped off when it completes. If a function returns a value, it typically ends the execution of that function, but otherwise that occurs when the last line of code in that function finishes running. A function isn’t popped off the stack until execution finishes, and if that function invokes another function – even another copy of itself, that function is pushed on top of the function that called it.**