# longest-parentheses-substring

## Question:
Write a program: Given a string containing just the characters '(' and ')', return the length of the longest valid (well-formed) parentheses substring.

Example 1:Input: s = "(()"Output: 2Explanation: The longest valid parentheses substring is "()".

Example 2:Input: s = ")()())"Output: 4Explanation: The longest valid parentheses substring is "()()".

Example 3:Input: s = ""Output: 0

Constraints:
0 <= s.length <= 3 * 104 | s[i] is '(', or ')'.

 # Thoughts:

 1. All the test cases had "()()()" type sequence which made me think if I just require simple if else statement. 
 2. So, I created a test case which nested parentheses to challenge my initial thought.
 3. After the test, I confirmed that I'll require stack and a maximum counter to keep track of maximum length of the substring.
 4. I used stack = [-1] to handle valid substrings starting at index 0 and to establish an initial boundary.
 5. When iterator comes to "(", I append the index of the parentheses and move forward.
 6. When iterator comes to ")", I first pop the last element, then there could be two ways to handle this:
    
    6.1. If stack is empty, then I just append the current index for it to become a new boundary.
    
    6.2. If stack is not empty, I calculate maximum = max(maximum, i - stack[-1]).
