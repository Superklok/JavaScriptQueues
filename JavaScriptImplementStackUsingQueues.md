# JavaScript Implement Stack Using Queues

## Challenge:

Implement a last-in-first-out (LIFO) stack using only two queues. The implemented stack should support all the functions of a normal stack (`push`, `top`, `pop`, and `empty`).

Implement the `MyStack` class:
<br/>
`void push(int x)` Pushes element x to the top of the stack.
<br/>
`int pop()` Removes the element on the top of the stack and returns it.
<br/>
`int top()` Returns the element on the top of the stack.
<br/>
`boolean empty()` Returns `true` if the stack is empty, `false` otherwise.

Notes:
<br/>
You must use only standard operations of a queue, which means that only `push to back`, `peek/pop from front`, `size` and `is empty` operations are valid.
<br/>
Depending on your language, the queue may not be supported natively. You may simulate a queue using a list or deque (double-ended queue) as long as you use only a queue's standard operations.

### 1<sup>st</sup> Example:

`Input: ["MyStack", "push", "push", "top", "pop", "empty"]`
<br/>
`[[], [1], [2], [], [], []]`
<br/>
`Output: [null, null, null, 2, 2, false]`
<br/>
`Explanation: MyStack myStack = new MyStack();`
<br/>
`myStack.push(1);`
<br/>
`myStack.push(2);`
<br/>
`myStack.top(); // return 2`
<br/>
`myStack.pop(); // return 2`
<br/>
`myStack.empty(); // return False`

### Constraints:

`1 <= x <= 9`
<br/>
At most `100` calls will be made to `push`, `pop`, `top`, and `empty`.
<br/>
All the calls to `pop` and `top` are valid.

## Solution:

`class MyStack {`
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`constructor() {`
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`this.queue = [];`
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`}`
<br/>
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`push(x) {`
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`this.queue.push(x);`
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`}`
<br/>
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`pop() {`
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`for(let i = 1; i < this.queue.length; i++) {`
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`this.queue.push(this.queue.shift());`
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`}`
<br/>
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`return this.queue.shift();`
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`}`
<br/>
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`top() {`
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`for(let i = 1; i < this.queue.length; i++) {`
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`this.queue.push(this.queue.shift());`
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`}`
<br/>
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`let temp = this.queue.shift();`
<br/>
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`this.queue.push(temp);`
<br/>
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`return temp;`
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`}`
<br/>
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`empty() {`
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`return this.queue.length === 0;`
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`}`
<br/>
`};`
<br/>
<br/>

## Explanation:

I've defined a class called `MyStack`. This class represents a stack data structure implemented using an array. This class has several methods for manipulating the stack.
<br/>

The constructor initializes an empty array called `queue`.
<br/>

The `push(x)` method adds an element `x` to the end of the `queue` array.
<br/>

The `pop()` method removes and returns the top element of the stack. It does this by iterating through the `queue` array from index `1` to the end. For each iteration, it removes the first element of the `queue` array and adds it to the end. Finally, it removes and returns the first element of the `queue` array.
<br/>

The `top()` method returns the top element of the stack without removing it. It follows the same process as the `pop()` method, but instead of removing the first element of the `queue` array at the end, it stores it in a variable called `temp`, adds it back to the end of the `queue` array, and then returns the value of `temp`.
<br/>

The `empty()` method checks if the `queue` array is empty and returns a boolean value indicating whether it is empty or not.
<br/>

In summary, this class implements a stack data structure using an array. The `push()` method adds elements to the stack, the `pop()` method removes and returns the top element, the `top()` method returns the top element without removing it, and the `empty()` method checks if the stack is empty.
<br/>
<br/>