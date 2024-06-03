Find the two non-repeating elements in an array of repeating elements where each element appears twice except those 2 elements
Intuition : 
In case of only one non repeating element in an array of elements where each element appears twice except that one , we apply xor operator on all the elements and eventually we are left with only that one element which is non repeating as XOR operation's Truth table is :
A           B              A^B 
0           0               0
0           1               1
1           0               1
1           1               0

Hence to solve this question in T.C of O(n) we need to optimise it using XOR operation .

Approach :
Single-handedly this is the most optimal approach one can move on to after trying brute force , so in steps it is as:
i)The XOR operation on all the elements has to be applied and eventual what we will be left with will be xorresult which is just those two non repeating numbers xor result.
ii) We have to find the first setbit in xorresult using 2's complement method .
    int setbit=(xorresult) & (-xorresult);
iii)The first setbit will be at the same position in some elements and in other element it won't be , out task is to find a group of those elements in which it is present and in another grp the rest of them .
    
    int divider= element of array & setbit 
    if(divider==0)
    {
       grp1=grp1^element;
    }
    else
    {
      grp2=grp2^element;
    }

iv) We did xor parallely and accumulate the result in g1 and g2 , the left g1 and g2 will be those two non repeating numbers.

Explanation :
int array=[1,2,3,2,5,1]
i) When we applly xor operation on elements the equal integers will get cancelled out and what's left is the xor result of two non repeating elements. eg: 1^2^3^2^5^1=6(110)
ii) Then when we find the first set bit it is naturally present in one of the two non repeating numbers that is in case of 3 (011) and 5(101) the result comes out to be 6(110) coz the 1 at any position is due to xor of either 0 and 1  or 1 and 0.
iii) We make groups that is if a number appears twice hence in either group number will be present with it's pair and will cancel out in xor . The non repeating number will fall into either one group and hence they will get seperated alongwith the repeating numbers cancelling out in parallel xor .


Overall : Inutitive question with bit manipulation , the (iii) step is crucial and ingenious move too.



