## QUEUE
- similar to lists, but they have rules about the order in which you can access their contents
- These rules make them useful for emulating real-life construct
- similar to a stack, but it uses First In, First Out (FIFO) ordering
- the only real difference between a stack and a queue is that stacks are Last In First Out, while queues are First In First Out
- removing or peeking from a queue should return the oldest element, while popping or peeking from a stack should return the newest.
**The first person to arrive becomes the front of the line, and every new person goes to the back of the line. When you need to remove a person from the line, you always remove from the front – the first person to arrive, who’s been waiting there the longest.**
_______________________________________

Queues have adding, removal, and peeking functionality just like stacks – save that they call them “adding” and “removing” instead of “pushing” and “popping”
 - can be implemented with a linked list, so long as you make sure to add and remove accordingly
 - In this case, adding an item to the back of the list might not operate in constant time, you’d have to iterate over the entire list to get to the current last item before you could add a new one
 - You can improve this by using a circular doubly-linked list, in which you can always access the last node directly from the head. This means you won’t have to iterate over the entire list to get to the last item. 
 
 ### Usage
 - typically used for scheduling certain events to happen

    **A computer processor core for example, can typically do only one thing at a time. It might do one million operations in a second, but it does each one in order. Computers often make use of queues to line up operations for a processor, even while it’s in the middle of doing something else.**

 - can also be used in some kind of searching algorithms
 **Envision trying to find your way through a maze with each intersection you come across, you choose one path and queue the others for exploration later. So once again, let’s look at an example algorithm question that uses our understanding of both stacks and queues – how could you implement a queue using two stacks?** 
 
 
1. We can use our two stacks then to divide the elements into a stack of the newest elements, and a stack of the oldest
- When a new item is added to the queue, it is pushed onto the newest stack
- When an item is removed or peeked, the corresponding operation is performed on the oldest stack
- When the oldest stack is empty, all the newest items are popped from the newest stack and popped onto the oldest stack
- This reverses their order, so the newest item in the newest stack goes to the bottom of the oldest stack, and thus will get popped or peeked last
- When the last item is removed from the oldest stack, the oldest stack is refreshed – again in reverse order – from the newest stack.Unfortunately, we can’t guarantee that add, remove, and peek operations work in O(1) time here.
- They will in the best-case scenario, but in the worst-case scenario the remove and peek operations will need to transfer all the old items from the newest stack into the oldest stack first, which could be an O(n) operation.Up until now we’ve been writing algorithms as standalone procedures

**Some algorithms are written like this, but in object oriented programming languages you’ll often see algorithms written as functions contained inside a structure like a class. It’s the same idea, but the rules for invoking the algorithms is a little different.You invoke the function that belongs to the structure, and send in the inputs between parenthesis.Again, the exact implementation of these structures, functions, and algorithms will depend on the language you are using**