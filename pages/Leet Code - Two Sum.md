-
- ### Two sum
	- Given an array of integers `nums` and an integer `target`, return _indices of the two numbers such that they add up to `target`. You may assume that each input would have **_exactly_ one solution**, and you may not use the _same_ element twice. You can return the answer in any order. #card #easy
	  id:: 6a28326d-1b20-4927-84ee-c675794ce5bc
		- https://leetcode.com/problems/two-sum/description/
		- Logical thinking: Without implementation
		  Brute force: Have two loops and iterate over the elements. The 2nd loop should start one element after first and the first loop should end before the last
		- Using the hashing
		- Using the two pointer approach
		- To use the two-pointer approach for this specific problem, you must first pair each number with its original index, sort the pairs by their values, and then use two pointers to find the target. [[1](https://medium.com/@AlexanderObregon/solving-the-two-sum-problem-on-leetcode-swift-answers-walkthrough-d076a8a709da), [2](https://medium.com/analytics-vidhya/array-two-pointers-4b8d62d2b8a), [3](https://medium.com/@srushtipillare/dsa-series-6-two-sum-04997b73a057)]
		- This approach achieves **\(O(n \log n)\) time complexity** due to sorting, and **O(n) space complexity** to store the elements alongside their original indices. [[1](https://www.tryexponent.com/courses/swe-practice/two-pointer), [2](https://medium.com/@AlexanderObregon/solving-the-two-sum-problem-on-leetcode-php-answers-walkthrough-fff20c9b3149)]
		- The Algorithm Steps
			- 1.  **Create an indexed array**: Map each element into a tuple or array containing `(value, original_index)`. [[1](https://medium.com/@mrinmayeerane2810/solving-the-two-sum-problem-two-pointer-approach-87cecd6dfe07)]
			- 2.  **Sort the array**: Sort these tuples based on the values in ascending order. [[1](https://codesignal.com/learn/courses/master-dictionaries-two-pointers-and-more-algorithms-in-python/lessons/manipulating-arrays-with-hashing-and-two-pointers-technique), [2](https://levelup.gitconnected.com/microsoft-dsa-interview-questions-2a1a5a12d8bf)]
			- 3.  **Initialize two pointers**: Place a `left` pointer at the start (index `0`) and a `right` pointer at the end (index `n - 1`). [[1](https://medium.com/@abidshafee/exploring-the-two-pointer-technique-an-essential-tool-for-array-and-linked-list-problem-solving-9c198ef5b9a1), [2](https://medium.com/@AlexanderObregon/solving-the-two-sum-problem-on-leetcode-swift-answers-walkthrough-d076a8a709da), [3](https://levelup.gitconnected.com/uacifds-unfold-ksum-family-problems-f27221357c92), [4](https://medium.com/@kiranpesarlanka9/283-move-zeroes-78684d396a64), [5](https://medium.com/@siva-sri/day-1-two-sum-e54354f2f1ab)]
			- 4.  **Evaluate the sum**:
				- If `sum == target`: Return the original indices of both pointers.
				- If `sum < target`: Move the `left` pointer to the right to increase the sum.
				- If `sum > target`: Move the `right` pointer to the left to decrease the sum. [[1](https://baotramduong.medium.com/leetcode-pattern-tips-strategies-for-solving-the-two-pointers-problem-3e0e6e5a08e6), [2](https://www.linkedin.com/pulse/leetcode-two-sum-anup-kumar-bid), [3](https://www.linkedin.com/pulse/exploring-two-sum-problem-two-pointer-approach-jean-claude-adjanohoun-xjn6c), [4](https://nikhilgupta1.medium.com/two-sum-array-problem-cceb7dc55008)]
			- Python Code Implementation
		- ```python
		  class Solution:
		      def twoSum(self, nums: list[int], target: int) -> list[int]:
		          # Step 1: Create a list of pairs (value, original_index)
		          indexed_nums = [(num, i) for i, num in enumerate(nums)]
		          # Step 2: Sort the pairs based on the values
		          indexed_nums.sort(key=lambda x: x[0])
		          # Step 3: Initialize pointers
		          left = 0
		          right = len(nums) - 1
		          # Step 4: Two-pointer traversal
		          while left < right:
		              current_sum = indexed_nums[left][0] + indexed_nums[right][0]
		              if current_sum == target:
		                  return [indexed_nums[left][1], indexed_nums[right][1]]
		              elif current_sum < target:
		                  left += 1
		              else:
		                  right -= 1
		          return []
		  ```
		-
	-