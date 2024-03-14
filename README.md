Ques 71:
Simplify Path
Initially , I read and comprehended this question to be another of the String type notation where the manipulation of String is through the methods in STL . Therefore , wrote a code which worked till 59 TestCases and then miserably didn't work even after 100 rectifications beacuse after all the root of the algortihm was wrong , all blame on me . 
This is the Code I wrote which was based on an apparently erroenous comprehension :

class Solution {
    public String simplifyPath(String path) 
    {
        Queue<String> queue = new LinkedList<>();
        String[] a = path.split("");
        Queue<String> queue2= new LinkedList<>();
        for (int i = 0; i < path.length(); i++) 
        {
            if ((a[i].equals("/")) && (!a[i].equals(".")) || (!a[i].equals("/") && !a[i].equals("."))) {
                queue.add(a[i]);
            }
        }
       
        String ans ="";
        while(!queue.isEmpty())
        {
            String c=queue.remove();
            if(!(c.equals("/") && queue.peek().equals("/")))
            {
             ans =ans+c;
            }
          }  
    return ans;
    }
}
}


Approach :
Then I looked over Internet to search up for some explanation about this question's language and then eventually I boiled down to the actual thing this question is asking , wrote a code with the following approach:
i) The String provided has characters such as / ,// , . , .. and the Alphabets (Ascii values from 97-122).
ii) How I understood this question :
~The /(name) defines a certain directory .
~ (.) defines to stay in the same directory.
~ (..) Defines to go back to the previous directory from the current directory .
~The simplified path should start from /.

Now , the whole problem has been dug down to the steps of popping when (..) is encountered and pushing in the Deque when /(name) is met.

iii) The array splits at the regex:"/"  in String which provides us an array of only (alphabets) and (.) and (..)
iV) Logic:
Tranversing through the array when (..) is met with pop out of Deque from last whilst checking that deque isn't empty.
If any element other than (..) && (.) && ()[empty] is met with push the element inside the Deque.
(Got Stuck as !c.isEmpty() worked where c!="" didn't )

v) Later when the TRansevrsal of the array ends then Build the String by removingfirst from deque using StringBuilder bcoz it provides Library of functions which benefits of time complexity paradigm.
vi) When each element is popped from first of Deque a "/" added to preceed it with .
ans.append.("/").append("deque.removeFirst());
vii) Return String ans2 by converting ans from StringBuilder to String using ans.toString();

Edge Case : 
Input : "/../" , arrray= ".." , deque=[] , ans="", ans2="" 
As the ans2 is empty then return "/"to represent the Empty Directory.

    
