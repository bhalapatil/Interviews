# Hash tables
	- How are hash tables implemented using the hash functions and linked list ? #card
	  id:: 6a34a915-119d-48fd-a289-b3e32f74ea1e
		- The hash function is used to calculate an int or long using the key as input from the hash function. Then the hash index is used as an index into an array at which the key and the value is stored
	- How are collisions handled in the Hash table? #card
	  id:: 6a34a920-1c54-4ff4-b618-92222e813273
		- A linked list is maintained at each index and collisions are handled
	- What the different names used in  Hash tables? #card
	  id:: 6a34a9d0-490e-419b-a635-a319d33641a7
		-
		- A hash table is a data structure used to store key-value pairs for highly efficient retrieval. Depending on the programming language, context, or theoretical computer science perspective, it goes by several other names. [[1](https://datastructures.maximal.io/hash-tables/)]
		- The most common alternative names include:
			- **Hash Map:** A term commonly used in Java and C++.
			- **Dictionary:** The standard term used in Python, C#, and Swift.
			- **Associative Array:** The formal mathematical or computer science term used for a collection of unique keys mapped to values.
			- **Map:** A shorter, common alias used broadly across many modern programming languages.
			- **Symbol Table:** Often used in compiler design and theoretical computer science to refer to a data structure that tracks information like variable names. [[1](https://medium.com/@poojadas053/hash-table-beea12d978b4), [2](https://study.com/academy/lesson/hash-tables-definition-use-functions.html), [3](https://www.cs.cornell.edu/courses/cs3110/2017fa/l/15-hashtable/notes.html), [4](https://ethans.co.in/blogs/hashmap-vs-hash-table-understanding-the-differences/), [5](https://datastructures.maximal.io/hash-tables/)]
		- Depending on specific implementation variations, you may also encounter terms like **Hash Set** (which stores only keys without accompanying values) or **Distributed Hash Table** (a decentralized variant used in distributed computing networks)
	- Ch1 : Q1 : Write a implementation of the hash table with arrays and linked list in c ? #card #cprogramming
	  id:: 6a34aa3d-9bb6-41c4-99e5-b4a5ad827c91
		-
- # ArrayList and Resizeable Arrays
	- In some languages, arrays (often called lists ) are automatically resizeable. The array list or list will grow as you append items. In other languages the arrays are fixed length. the size is defined when you create the array
	- #+BEGIN_IMPORTANT
	  This is an important data structure for the interviews
	  #+END_IMPORTANT
	- How is any arraylist of the List in python implemented? Can you implement in C to store int values? #card #cprogramming
	  id:: 6a34abd4-7633-4115-8c08-1fd010554c51
	- How do you extend the arraylist data structure to store values of any type ? #card #cprogramming
	  id:: 6a34ac20-add8-44cb-8fa3-e2af8695783b
		- Hint : using macros
	- What will be the amortized runtime of the insertion into an list ? #card
	  id:: 6a34acf3-de45-40f0-b207-9e8d1a1b5359
		- O(1) . Suppose you have a list of size N, We can work backwards to compute how many elements are copied as the size increases. When we increase the array to K elements, the array was K/2 previously. Therefore we need to copy k/2 elements
		- ```
		  final capacity increase : n/2 elements to copy
		  previous capacity increase : n/4 elements to copy
		  previous capacity increase :: n/8 elements to copy
		  ....
		  second capacity increase : 2 elements to copy
		  first capacity increase : 1 element to copy
		  ```
		- The addition of this series is N/2 + N/ 4 + N/8 ...2 + 1. This is approximately N
- # Exercises
	- Is Unique : Part 1 :  Implement an algorithm to determine if a string has all unique characters? What will be the Space and time complexity ? #card
	  id:: 6a34b240-f32a-4615-8a90-6147a7a7c44c
		-
	-
	- Is Unique : Part 2 : What if you cannot use any other additional data structures? What will be the space and time complexity ? #card #cprogramming
	  id:: 6a34b27e-1559-4541-984a-f4e675614da9
		-
	- Check Permutation: Given two strings, write a method to decide if one is a permutation of the other? #card
	  id:: 6a3ab47b-e7eb-4036-88e5-a9c5c35a3c3c
		- Hint: How do you decide that on string is a permutation of the other?
		- Two strings are a permutation of each other if the char counts are the same. To implement this we can use a dictionary and then compare the dictionaries
		- Important : You should not assume that the permutation is case insensitive. "God" is different from "dog". Also, you can check if the spaces are significant. i.e. if "God" is different from "God     ". If spaces are not significant then you should trim the string
		- ```python
		  import unittest
		  
		  
		  def isPermutation(s1: str, s2: str) -> bool:
		      d1 = {}
		      d2 = {}
		      for s in s1:
		          if s in d1:
		              d1[s] = d1[s] + 1
		          else:
		              d1[s] = 1
		  
		      for s in s2:
		          if s in d2:
		              d2[s] = d2[s] + 1
		          else:
		              d2[s] = 1
		      return d1 == d2
		  
		  
		  # step1 : Create a test class inheriting from the unittest.TestCase
		  
		  class check_permutations(unittest.TestCase):
		  
		      # Step2 : Create method that start with test
		      def test_input1(self):
		          result = isPermutation("god", "dog")
		          self.assertTrue(result)
		  
		      def test_input2(self):
		          result = isPermutation("god ", "dog")
		          self.assertEqual(result, False)
		  
		      def test_input3(self):
		          result = isPermutation("God ", "dog")
		          self.assertEqual(result, True)
		  
		  
		  if __name__ == "__main__":
		      unittest.main()
		  ```
	- URLify: Write a method to replace all the spaces in a string with "%20". #card
	  id:: 6a3ab47b-e958-4973-9d76-da6cb3ff450e
		- Hint: Count the number of characters in the string and how much is needed later
	- Palindrome permutation: Given a string, write a function to check if it is a permutation of a palindrome.
	  id:: 6a3ab47b-e5a8-46da-8e64-3c5d8924e194
		- What is a palindrome? What are the possible cases (even , odd) and what is are the features
		- Solution 1: check the input string and ensure that there is no more than on character with an odd count
		- ```python
		  import unittest
		  from typing import Dict
		  
		  
		  def get_char_count(input: str) -> Dict[str, int]:
		      freq = dict()
		      for x in input:
		          s = x.upper()
		          if s in freq:
		              freq[s] = freq[s] + 1
		          else:
		              freq[s] = 1
		      return freq
		  
		  
		  def is_palindrome(input: str) -> bool:
		      freq = get_char_count(input)
		      odd_found = False
		      for (k, v) in freq.items():
		          if (v % 2) == 1:
		              if odd_found:
		                  return False
		              odd_found = True
		          else:
		              return True
		  
		  
		  class check_palin_permutation(unittest.TestCase):
		  
		      def test_input1(self):
		          self.assertTrue(is_palindrome("Tact Coa"))
		  
		      def test_input2(self):
		          self.assertFalse(is_palindrome("cat"))
		  
		  
		  if __name__ == "__main__":
		      unittest.main()
		  ```
		- Why is it sufficient to check this condition alone?
		- What would be the logic if you assumed english alphabets and if you want to implement this using a bit vector
		-
	- Single Edit: There are 3 types of edits that can be performed on strings: insert a character, remove a char or replace a char. Given two strings, write a function to check if they are one edit (or zero edits) away
		- Ex:
		  pale , ple -> true
		  pales , pale -> true
		  pale , bale -> true
		  pale , bake -> false
		- ```python
		  import unittest
		  
		  
		  def is_single_edit(s1: str, s2: str) -> bool:
		      result = True
		      idx1 = 0
		      idx2 = 0
		      # remove any spaces
		      s1 = s1.strip()
		      s2 = s2.strip()
		      edit_type = None
		  
		      # check for any empty strings
		      #
		      if len(s1) <= 0 or len(s2) <= 0:
		          return False
		      while True:
		          # either of the string is complete and so far there is only one edit and hence return true
		          if ((idx1 + 1 == len(s1)) or (idx2 + 1 == len(s2))):
		              if edit_type:
		                  return T/rue
		              else:
		                  if abs(len(s1) - len(s2)) == 1:
		                      return True
		                  else:
		                      return False
		  
		          # both the chars are matching. Increment both of the them
		          if s1[idx1] == s2[idx2]:
		              idx1 += 1
		              idx2 += 1
		          # string1 next char is the same the string2 curr char. Thne
		          # deleting the curr char in string1 can be done if this is the first edit
		          # Else it is fail case
		          elif s1[idx1 + 1] == s2[idx2]:
		              if edit_type:
		                  return False
		              else:
		                  edit_type = "delete"
		                  idx1 = idx1 + 1
		          elif s1[idx1] == s2[idx2 + 1]:
		              if edit_type:
		                  return False
		              else:
		                  edit_type = "insert"
		                  idx2 = idx2 + 1
		          elif (s1[idx1] != s2[idx2]) and (s1[idx1 + 1] == s2[idx2 + 1]):
		              if edit_type:
		                  return False
		              else:
		                  edit_type = "modify"
		                  idx1 += 1
		                  idx2 += 1
		  
		      return True
		  
		  
		  
		  class check_single_edits(unittest.TestCase):
		      def test_input1(self):
		          result = is_single_edit("test", "tst")
		          self.assertTrue(result)
		  
		      def test_input2(self):
		          result = is_single_edit("tst", "test")
		          self.assertTrue(result)
		  
		      def test_input3(self):
		          result = is_single_edit("tart", "mart")
		          self.assertTrue(result)
		  
		      def test_input5(self):
		          result = is_single_edit("tart", "mast")
		          self.assertFalse(result)
		  
		      def test_input6(self):
		          result = is_single_edit("x", "mast")
		          self.assertFalse(result)
		  
		      def test_input7(self):
		          result = is_single_edit("tste", "tst")
		          self.assertTrue(result)
		  
		  
		  if __name__ == "__main__":
		      unittest.main()
		  
		  ```
	- String compression: Implement a method to perform basic string compression using counts of repeated chars. For ex: the string aabcccccaaa would be a2b1c5a3. If the compressed string would not  become smaller than the original string, you method should return the orginal string. You can assume the string has only uppercase and lowercase letters (a -z)
	  id:: 6a475da3-391d-445c-98dc-93fa026439b5
	  #card
		- Hint: Underlying concept is the same - character frequency
	- String Rotation: Assume that you have a method isSubstring that check if one string is a substring of the other. Write a function that takes two string and checks if one is a rotation of the other? #card
	  id:: 6a47a42e-29b7-4b36-9f4a-ff43fd400f9a
		- See the hints in the book and solve
	- Rotate Matrix: Given an image represented by NxN matrix, where each pixel is in the image is 4 bytes. Write a method to rotate the image by 90 degrees. Can you do this in place?
		- Watch the striver's video : {{video https://www.youtube.com/watch?v=Z0R2u6gd3GU&t=466s}}
		- See book, page 151 for the solution.
		- The task is to convert into python and write the unit test cases
	- Zero matrix: Write an algorithm such that if an element in an MxN matrix is 0, its entire row and column are set to 0.
		- Watch stiver's video
		- {{video https://www.youtube.com/watch?v=N0MgLvceX7M}}
		-
	-
	-