- https://leetcode.com/problems/add-two-numbers/description/
- You are given two **non-empty** linked lists representing two non-negative integers. The digits are stored in **reverse order**, and each of their nodes contains a single digit. Add the two numbers and return the sum as a linked list.
- You may assume the two numbers do not contain any leading zero, except the number 0 itself.
-
- ```python
  # Definition for singly-linked list.
  # class ListNode:
  #     def __init__(self, val=0, next=None):
  #         self.val = val
  #         self.next = next
  class Solution:
      def getNumber(self ,l : ListNode) -> int :
          curr = l
          exp = 1
          num = 0
          while(curr):
              num = num + curr.val * exp
              exp = exp * 10
              curr = curr.next
          # print(f" num : {num}")
          return num
          
      def addTwoNumbers(self, l1: Optional[ListNode], l2: Optional[ListNode]) -> Optional[ListNode]:
          num1 = self.getNumber(l1)
          num2 = self.getNumber(l2)
          num = num1 + num2
          snum = str(num)
          prev = None
          curr = ListNode(int(snum[0]))
          for i in range(1 , len(snum)):
              # print(f"Adding {snum[i]}")
              prev = curr
              curr = ListNode(int(snum[i]))
              curr.next = prev
          return curr
  ```
-
-