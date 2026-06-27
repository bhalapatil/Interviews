- Write a function to find the longest common prefix string amongst an array of strings.
- https://leetcode.com/problems/longest-common-prefix/description/
-
-
-
- If there is no common prefix, return an empty string `""`.
	- Logic 1 :
		- Take the first string as the starting point.
		- For each character in the string 1, check the other strings and check if they are matching. If matching go to the next character. Else return the characters matched so far
		- ```python
		  class Solution:
		      def longestCommonPrefix(self, strs: List[str]) -> str:
		          if not strs:
		              return ""
		          
		          for i in range(len(strs[0])):
		              char = strs[0][i]
		              for s in strs[1:]:
		                  # If we reach the end of a string or characters don't match
		                  if i == len(s) or s[i] != char:
		                      return strs[0][:i]
		          
		          return strs[0]
		  ```
	- Logic 2:
		- Sort all the strings and then match first and the last string. Since it is longest common prefix it the first and the last match then it should match others also
		- ```python
		  class Solution:
		      def longestCommonPrefix(self, strs: List[str]) -> str:
		          if not strs:
		              return ""
		          
		          strs.sort()
		          first, last = strs[0], strs[-1]
		          
		          i = 0
		          while i < len(first) and i < len(last) and first[i] == last[i]:
		              i += 1
		              
		          return first[:i]
		  
		  ```
	- My Solution: Using list expressions- Not the optimal solution
		- ```python
		  class Solution:
		      def longestCommonPrefix(self, strs: List[str]) -> str:
		          sizes = [len(s) for s in strs]
		          matching_chars = []
		          min_size = min(sizes)
		          print("min size string" , min_size)
		          for i in range(0 , min_size):
		              pos_chars = [s[i] for s in strs]
		              print(pos_chars)
		              char_set = set(pos_chars)
		              print("set " , char_set)
		              if len(char_set) == 1:
		                  matching_chars.append(pos_chars[0])
		              else:
		                  break
		                  
		          print("matching chars" , "".join(matching_chars))
		          return "".join(matching_chars)
		  ```
	-