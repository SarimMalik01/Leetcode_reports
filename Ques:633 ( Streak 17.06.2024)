Ques : 633  
Sum of square numbers 
Problem Statement : To check if the Sum of any 2 Integers is equal to the given number and if such a pair doesn't exist return false else return true.
Approach : 1
Hashing Approach :
T.C :  𝑂(√𝑐) due to the need to compute squares and perform lookups.
S.C :  𝑂(√𝑐) due to the need to store squares of Integers in HashSet upto √c . 
This intutitive approach was thought of due to the O(x²) : {n=x} in two loops to find the valid pair of Integers such that their sum of squares is eqaul to c.
The approach proceeds as :
1)Store the Square of Integers upto √c in the HashSet.
2)Then iterate through the map to find whether any b exists in Set such as which suits this condition
      : b²=c-a²
if there is such a b in set return true lest at the end of iteration return false
Code : 
public static boolean judgeSquareSum(int c) {
    HashSet<Integer> squares = new HashSet<>();
    for (int i = 0; i <= Math.sqrt(c); i++) {
        squares.add(i * i);
    }
    for (int a : squares) {
        if (squares.contains(c - a)) {
            return true;
        }
    }
    return false;
}
Drawbacks : This approach leads to a S.C in which we have to store a set of space √𝑐 which might work for a smaller value of c but collapses when the value of c is larger such as this ((2^31) - 1) hence there's a need for better approach.

Approach:2 
Binary Approach 
T.C :  𝑂(√𝑐) due to the need to compute squares and perform lookups.
S.C :  𝑂(1) 
This approach originates from the Binary Search algorithm where a set of two pinters move left or right according to the given sum , product , difference if it meets the required value which in this case is c.
Why √𝑐 and not just c for the above and this approach too ?
As a²+b²=c then it is inferred that the following condition must also stay true for a and b
                   a≤√𝑐   and b≤√𝑐  
if any a or b violates the rule then the condition of sum isn't met and this will be the sum a²+b²>c
The approach proceeds as :
1)Initialisation of two pointers left and right( a and b) left=0 (lowest integer which is !negative & ! positive) and right=√𝑐 .
2)The left and right pointer serve as the two extremes of the pair of values which might be present between .
3) If the sum of left's and right's squares is more than c , right pointer decrements else left pointer increments. To keep updation of their sum as with each iteration it steps closer to c till left<=right pointer .
4) Once sum is found , true is returned and if the iteration of loop succumbs to cease then false is returned.

Code:
public static boolean judgeSquareSum(int c) {
    int left = 0;
    int right = (int) Math.sqrt(c);
    
    while (left <= right) {
        int sum = left * left + right * right;
        if (sum == c) {
            return true;
        } else if (sum < c) {
            left++;
        } else {
            right--;
        }
    }
    
    return false;
}

Conclusion:

~ Both approaches have the same time complexity but differ significantly in space complexity.
~ For larger values of c the binary approach is more suitable .
~ The mathematical property of if  a²+b²=c  then  a≤√𝑐   and   b≤√𝑐  is leveraged and effectively used.
