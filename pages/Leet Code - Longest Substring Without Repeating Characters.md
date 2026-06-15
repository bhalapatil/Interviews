- Given a string `s`, find the length of the **longest** **substring** without duplicate characters.
- **Example 1:**
- ```
  **Input:** s = "abcabcbb"
  **Output:** 3
  **Explanation:** The answer is "abc", with the length of 3. Note that `"bca"` and `"cab"` are also correct answers.
  ```
- **Example 2:**
- ```
  **Input:** s = "bbbbb"
  **Output:** 1
  **Explanation:** The answer is "b", with the length of 1.
  ```
- **Example 3:**
- ```
  **Input:** s = "pwwkew"
  **Output:** 3
  **Explanation:** The answer is "wke", with the length of 3.
  Notice that the answer must be a substring, "pwke" is a subsequence and not a substring.
  ```
-
- Solution  1 : Brute -force
- Solution 2: O(N) by using the sliding window technique
	- The sliding window technique has two indices/pointers. start and end. This will refer to a window in the substring that is unique. The start is initialized to beginning and the end iterates till the end of the string
	- A dictionary is used to keep track of the characters seen in the window so far along with the index where it appears in the string. This is called the seen.
	- Every time a new character is encountered, it is added to the seen and the window is incremented.
	- When a character that is encountered is got, the start is moved to the character next to the duplicate character.
	- #+BEGIN_IMPORTANT
	  Ensure that the window boundaries are checked.
	  #+END_IMPORTANT
	- ```python
	  class Solution1:
	      def lengthOfLongestSubstring(self, s: str) -> int:
	          seen = {}
	          start = 0
	          max_length = 0
	  
	          for end in range(len(s)):
	              # If the character is repeated and is inside the current window
	              if s[end] in seen and seen[s[end]] >= start:
	                  start = seen[s[end]] + 1
	  
	              # Update or insert the current character's latest index
	              seen[s[end]] = end
	  
	              # Calculate the distance between pointers and update max
	              current_length = end - start + 1
	              if current_length > max_length:
	                  max_length = current_length
	  
	          return max_length
	  ```
		- Tests
		- s1.lengthOfLongestSubstring("abcabcbb")
		- s1.lengthOfLongestSubstring("dvdf")