- Given a number, check if its a palindrome and return true or false
  Ex : 121 - is a palindrome
	- https://leetcode.com/problems/palindrome-number/description/
	-
	- Solution Approach:
	- The alrorithm uses the two pointer pattern having a start and end indices and pointers.
	- The start and the end are checked if they are the same and then palindrome is checked
	-
	- ```python
	  class Solution:
	      def isPalindrome(self, x: int) -> bool:
	          num_str = str(x)
	          start = 0
	          end = len(num_str) - 1
	          while(start <= end - 1):
	              if (num_str[start] != num_str[end]):
	                  return False
	              else:
	                  start = start + 1
	                  end = end -1
	          return True
	  ```
	-
	-
	-
	-
	-