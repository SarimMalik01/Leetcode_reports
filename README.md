Ques 232:
Implement Queue using Stacks
Approach 1:
i) Initlaised 2 Stacks named them in_stack and out_stack .
ii)Using Myqueue constructor initliased them as the vairables of an object of class Myqueue when it is instantiated.
iii)In push Method , the elements are pushed inside the in_stack and then they are pushed in out_stack by popping out of the in_stack such that the elements which had entered at first inside the in_stack now appears at the top of the out_stack , hence the element which had entered first in in_stack can now be popped out of first from out_stack following FIFO.
iv)The other methods are also coded in the same way by pop , peek and checking empty stack in the out_stack.

The issue with this approach is the order of elements getting disturbed when you push each element in the in_stack and then push them inside the out_stack and the out_stack will not get changed in other Methods pop peek and empty .


Approach 2:
i) Initlaised 2 Stacks named them in_stack and out_stack .
ii)Using Myqueue constructor initliased them as the vairables of an object of class Myqueue when it is instantiated.
iii)In every Method except PUSH , the elements are pushed inside the in_stack and then they are pushed in out_stack by popping out of the in_stack such that the elements which had entered at first inside the in_stack now appears at the top of the out_stack , hence the element which had entered first in in_stack can now be popped out of first from out_stack following FIFO.
iv)The other methods are also coded in the same way by pop , peek and checking empty stack in the out_stack.

This approach solves the problem as it pushes the elements from in_stack to out_stack once it encounters the method call to empty , pop and peek.

Overall Review : This Question wouldn't have been solved if I hadn't drawn two stacks and a pipe like Queue to generate the idea.
