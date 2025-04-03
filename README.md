# Solution1 Reverse First k Elements of Queue
In this solution, we utilize a stack to reverse the order of the first k elements in the queue. The very first step is to check whether k is greater than the size of the queue, k is negative, or queue is empty. If any of this is the case, we return NULL, indicating that it cannot perform the reversal. Otherwise, the solution walks through the following steps:

We initialize an empty stack, stack, and dequeue the first k elements from the queue and push them into stack.

After storing the first k elements in Mystack, we need to restore them in queue. This effectively reverses the order of the first k elements utilizing the LIFO behavior of the stack.

For restoring elements, we pop each element from stack and enqueue it back into the queue. We do this until stack becomes empty. This step effectively restores the reversed elements, but now at the end of the queue.

After restoring the reversed elements, dequeue elements from the queue again, (size - k) times, i.e., the number of remaining elements in the queue. Enqueue these elements back into the queue. This step maintains the order of the remaining elements in the queue.

Finally, return the modified queue, where the first k elements are reversed while the remaining elements maintain their original order.

# Solution2 Sort Values in a Stack
The solution takes an iterative approach towards the problem. It starts by initializing a temporary stack to facilitate sorting. While the main stack contains elements, we compare each element with the top of the temporary stack. If the current popped element is larger or equal, we add it to the temporary stack; otherwise, we store it and rearrange the remaining elements of the main and temporary stack until the temporary stack’s top is smaller than the current element. The stored element is then pushed onto the temporary stack, and the steps are repeated until the main stack is empty. Finally, the temporary stack holds elements in descending order, which we transfer back to the main stack to achieve a sorted ascending order.
