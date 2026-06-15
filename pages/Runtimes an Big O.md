- What is time complexity ? #card
  card-last-interval:: -1
  card-repeats:: 1
  card-ease-factor:: 2.5
  card-next-schedule:: 2026-06-09T18:30:00.000Z
  card-last-reviewed:: 2026-06-09T13:06:21.953Z
  card-last-score:: 1
	- This means the time or # of steps an algorithm takes to complete given an input size of N. Some example of this is are O(N) , O(log N), $O(N^2)$ , O(N logN) etc
	- You can also have multiple variables in the runtime. For ex, to paint a fene that is w metres wide and h meters height, could be described as O(wh). If the paint is p layers then it is O(pwh)
- What are Big O , Big Theta and Big Omega ? #card
  card-last-interval:: 4
  card-repeats:: 1
  card-ease-factor:: 2.6
  card-last-reviewed:: 2026-06-09T13:07:29.983Z
  card-next-schedule:: 2026-06-13T13:07:29.982Z
  card-last-score:: 5
	- O (big O) : In academia describes the upper bound. This is similar to less than or equal to. For Ex : printing an array will take O(N). but it can also be mentioned as O($N^2$). The algorithm is atleast as fast as this. Ex: if a man lives for 130 years and your age is x, then x can be describes as , $x \le 130$ . It can be be said as $x \le 1000$
	- Big $\Omega$ : This describes the lower bound. This means that it will alteast that much time. Printing an array takes $\Omega(N)$ or $\Omega(1)$
	- \Theta : In academia \Theta means both  O and \Omega.  That is, an algorithm is \Theta(N) if it is both O(N) and \Omega(N). \Theta gives a tight bound on the runtime
	- #+BEGIN_IMPORTANT
	  In industry (an therefore in interviews) the concept of \Theta and O are merged together. Industry meaning of O is closer to what \Theta means in academics.
	  #+END_IMPORTANT
- What is Best Case, Worst Case and expected case ?  Explain using the Quick Sort #card
  card-last-interval:: -1
  card-repeats:: 1
  card-ease-factor:: 2.5
  card-last-reviewed:: 2026-06-09T13:09:41.393Z
  card-next-schedule:: 2026-06-09T18:30:00.000Z
  card-last-score:: 1
	- Best Case : If all elements are equal, then quick sort will, on average, just traverse through the array once.
	-
- What is space complexity? #card
  card-last-interval:: 4
  card-repeats:: 1
  card-ease-factor:: 2.6
  card-last-reviewed:: 2026-06-09T13:08:54.510Z
  card-next-schedule:: 2026-06-13T13:08:54.510Z
  card-last-score:: 5
	- Space complexity is the amount of memory (space) that is needed to execute the algorithm
- What is the space and time complexity of the below code? 
  card-last-interval:: 4
  card-repeats:: 1
  card-ease-factor:: 2.6
  card-last-reviewed:: 2026-06-09T13:09:30.908Z
  card-next-schedule:: 2026-06-13T13:09:30.908Z
  card-last-score:: 5
  ```c
  int sum(int n) {
    if (n <=0) {
      return 0;
    }
    return n + sum(n-1);
  }
  ```
  #card
	- Each call add to the stack.
	  sum(4)
	  -> sum(3)
	  -> -> sum(2)
	  -> -> -> sum(1)
	  -> -> -> sum(0)
	- Each of these calls is added to the call stack and takes up actual memory and hence is it O(n) for both time and space complexity. the stack is also added to the space complexity
- What is the space and time complexity of the below code? 
  card-last-interval:: -1
  card-repeats:: 1
  card-ease-factor:: 2.5
  card-last-reviewed:: 2026-06-09T13:12:37.228Z
  card-next-schedule:: 2026-06-09T18:30:00.000Z
  card-last-score:: 1
  ```c
  int pairSumSequence(int n) {
    int sum = 0;
    for (i =0 ; i < n ;i++) {
        sum += pairSum(i , i+1);
    }
  return sum;
  }
  
  int pairsum(int a , int b) {
     return a + b;
  }
  ```
  #card
	- Since each loop adds two consecutive elements and only one stack frame will exist for pairSum at any point. Hence it is O(1)
- What does drop the constants mean in the Big O analysis? #card
  card-last-interval:: 4
  card-repeats:: 1
  card-ease-factor:: 2.6
  card-last-reviewed:: 2026-06-09T13:07:40.644Z
  card-next-schedule:: 2026-06-13T13:07:40.643Z
  card-last-score:: 5
	- During the analysis the O(2N) will be changed to O(N). This is done because N is assumed to be sufficiently large.
- What is the runtime for the below code? 
  card-last-interval:: -1
  card-repeats:: 1
  card-ease-factor:: 2.5
  card-last-reviewed:: 2026-06-09T13:08:33.254Z
  card-next-schedule:: 2026-06-09T18:30:00.000Z
  card-last-score:: 1
  ```c
  int min = Integer.MIN_VALUE;
  int max = Integer.MAX_VALUE;
  int[] array = malloc(sizeof(int) * N);
  for (int i = 0 ; i < N ;i++) {
    if (x < min) min = x;
  }
  for (int i = 0 ; i < N ;i++) {
    if (x > max) max = x;
  }
  ```
  #card
	- You could say O(2N). But since the constants are dropped it is O(N)
- What do you mean by drop the non-dominant factors? #card
  card-last-interval:: 4
  card-repeats:: 1
  card-ease-factor:: 2.6
  card-next-schedule:: 2026-06-13T13:08:45.533Z
  card-last-reviewed:: 2026-06-09T13:08:45.533Z
  card-last-score:: 5
	- The factor  that has the highest exponent and ignore the rest. This is done because as N grows large the contribution of the non-dominant factors start becoming smaller and smaller compared to the dominant factor
-
- In which case should you add the runtimes and in which case you should multiple the,?
  card-last-interval:: 4
  card-repeats:: 1
  card-ease-factor:: 2.6
  card-next-schedule:: 2026-06-13T13:05:44.254Z
  card-last-reviewed:: 2026-06-09T13:05:44.254Z
  card-last-score:: 5
  case 1: 
  ```c
  for (int i=0 ;i < N ;i++) {
  printf("%d',a[i]); 
  }
  
  for (int i=0 ;i < N ;i++) {
  printf("%d',b[i]); 
  }
  ```
  case 2:
  ```c
  for (int i=0;i < N ;i++){
       for (int j=0;j< N;j++){
            printf("%d , %d",a[i] ,b[j];
     }
  }
  ```
  #card
	- Case 1: Add the runtimes
	  Case 2: Multiply the runtimes
	  In general; 
	  1. If your algorithm is in the form "do this, then, when you are all done, do that" then you add the runtimes
	  2. If your algorithm is in the form "do this for each time you do that" then you multiply the runtimes
	  
	  #+BEGIN_IMPORTANT
	  Its easy to mess this up in an interview !! So be careful
	  #+END_IMPORTANT
	-
- # Amortized time
	- What is amortized time?  Give an example ?
		- Mini programming languages contain an array called a Arraylist Or a dynamically resizable array. This allows the benefit of an array while offering flexibility in size. This won't run out of space since its capacity will grow as the elements are inserted. NRA list is implemented with an array When the array hits capacity The aerialist class will create a new array with double the capacity and copy all the elements over to the new array. How do you describe the runtime of insertion? #card
		  card-last-interval:: -1
		  card-repeats:: 1
		  card-ease-factor:: 2.5
		  card-next-schedule:: 2026-06-09T18:30:00.000Z
		  card-last-reviewed:: 2026-06-09T13:05:27.387Z
		  card-last-score:: 1
			- As we insert elements, we double the capacity when the size of the array is a power of 2. so after X elements, we double the capacity at array size 1+2+4+8....+X. Or in other words X+X/2 + X/4...+1. This is roughly 2X.
			  Therefore the insertion takes O(2X) time and the amortized time for each insertion is O(1)
- # Log runtimes
	- What is the runtime of the balanced binary search ? #card
	  card-last-interval:: 4
	  card-repeats:: 1
	  card-ease-factor:: 2.6
	  card-next-schedule:: 2026-06-13T13:03:11.548Z
	  card-last-reviewed:: 2026-06-09T13:03:11.550Z
	  card-last-score:: 5
		- O(log N). In general if the number of elements in the problem space gets halved each time, that will likely be a O(log N) runtime
- # Recursive
	- What is the runtime(time complexity) and space complexity and of this code? #card
	  card-last-interval:: 4
	  card-repeats:: 1
	  card-ease-factor:: 2.6
	  card-next-schedule:: 2026-06-13T13:04:06.466Z
	  card-last-reviewed:: 2026-06-09T13:04:06.466Z
	  card-last-score:: 5
	  ```c
	  int f(int n) {
	  if (n <= 1) {
	  return 1;
	  }
	    return f(n-1) + f(n - 1)
	  }
	  ```
	  #card
		- The tree will have a depth N, Each node branches into two children. Therefore each level will have twice as many calls as the one above it. In this case it will be $2^{(n+1)} -1$
		- This is a pattern, when there is a recursive function that makes multiple calls, the runtime will often (but no always) look like $O(branches^{depth}$, where branches is the number of times each recursive call branches. In this case, this gives $O(2^N)$
		- The space complexity will be O(N)
	- What is the space complexity of the code? 
	  card-last-interval:: -1
	  card-repeats:: 1
	  card-ease-factor:: 2.5
	  card-next-schedule:: 2026-06-09T18:30:00.000Z
	  card-last-reviewed:: 2026-06-09T13:02:44.894Z
	  card-last-score:: 1
	  ```c
	  int f(int n) {
	  if (n <= 1) {
	  return 1;
	  }
	    return f(n-1) + f(n - 1)
	  }
	  ```
	  #card
		-
		- O(n) - Why it is \(O(n)\) and not \(O(2^n)\)
		- It is a common misconception to assume that because this function makes two recursive calls per step (giving it a **time complexity** of \(O(2^n)\)), the space complexity must match. However, the computer executes these calls sequentially, not simultaneously.
			- 1.  **The Call Stack Depth**: When `f(n)` runs, it invokes the first `f(n-1)`. That call pauses the execution of the parent function and goes deeper, invoking `f(n-2)`, then `f(n-3)`, all the way down to the base case `f(1)`.
			- 2.  **Memory Recycling**: Once `f(1)` hits the base case, it returns its value and its memory frame is immediately popped off the call stack. Only then does the computer begin evaluating the second `f(n-1)` call.
			- 3.  **Maximum Height**: At any single point in time during execution, the call stack will never hold more than \(n\) active function frames.
		- Therefore, the maximum memory allocated on the call stack scales linearly with the input size, resulting in a space complexity of **\(O(n)\)**.
-
- # Exercises
	- Big O :Q1 : What is the runtime of the below code? Write the code and practise.
	  collapsed:: true
	  ```python
	  def foo(arr: list) :
	    sum = 0
	    product = 1
	    # first way to iterate an array
	    for i in range(0,len(arr)): 
	      sum += arr[i]
	    # second way to iterate an array
	    for x in arr: 
	      product *= x
	    # formatted strings
	    print(f" Sum is {sum} and product is {product}")
	  ```
	  #card
		- <answer>O(len(arr))
	- Big O: Q2 : What is the runtime of the below code ? Write the code and practise
	  collapsed:: true
	  ```python
	  def foo(arr: list) :
	    sum = 0
	    product = 1
	    # first way to iterate an array
	    for i in range(0,len(arr)):
	     	for j in range(0,len(arr)):
	    		print(f" i : {arr[i] j: arr[j]}
	  ```
	  #card
		- <Answer>
	- Big O: Q3 : What is the runtime of the below code ? Write the code and practise
	  collapsed:: true
	  ```python
	  def printUnrderedPairs(arr: list):
	    for i in range(0,len(arr)):
	      for j in range(i+1, len(arr)):
	        print(f"i : {arr[i] j: {arr[j]}})
	  ```
		- Show the analysis
	-
	- Big O: Q4 What is the runtime of the below code? Write the code and practise
	  collapsed:: true
	  ```python
	  from typing import List
	  def printUnrderedPairs(arr1: List , arr2:List):
	    for i in range(0,len(arr1)):
	      for j in range(i+1, len(arr2)):
	        print(f"i : {arr1[i] j: {arr2[j]}})
	  ```
		- This is O(ab) where a is the length of first array a and b the 2nd array
	-
	- Big O: Q5 The following code reverses an array. What is its runtime? 
	  ```python
	  def reverse(l : list):
	    for i in range(0,len(l)/2):
	      other = len(l) - i -1
	      temp = l[i]
	      l[i] = l[other]
	      l[other] = temp  ANS=O(N/2)
	  ```
	  #card
	- Big O: Q6 Which of the following are equivalent to O(N)? Why ?
	  collapsed:: true
	  1. O(N + P) where P < N/2
	  2. O(2N)
	  3.O(N + log N)
	  4.O(N + M)  
	  #card
		- ALL OF THEM ARE EQUAL - shreyas
	- Big O: Q7: Suppose we had an algorithm that took an array of strings, sorted each string and the sorted the full array, What would be the runtime? O(N^2)
	-
	- Bog O: Q8: The following code sums the values of all the nodes in a balanced binary tree? What is its time and space complexity ?
	  collapsed:: true
	  ```python
	  def sum(node : Node):
	    if not node:
	      return o
	    return sum(node.left) + node.value + sum(node.right)
	  ```
	  #card
		- O(LOGN) - shreyas
	- Big O : Q9 The following code checks if a number is prime. What is the time complexity of this? Why is the code checking only till the sqrt? 
	  collapsed:: true
	  ```python
	  bool isPrime(n : int):
	    for x in 2..range(math.sqrt(n) + 1): #why should 1 be added?
	      if (n % x == 0):
	        return false
	      
	    return true
	  ```
	  #card
		- O(LOGN) - shreyas
		-
	- Big O: Q10 The following code computes the factorial. What is its time and space complexity?
	  ```python
	  def factorial(n: int):
	    if n < 0:
	      return -1;
	    elif n == 0:
	      return 1
	    else:
	      return n * factorial(n -1)
	  ```
	  #card
		- O(N)
	- Big O: Q11 The code calculates the Nth Fibonnacci number. What is the time complexity?  
	  ```python
	  def fib( n : int):
	  	if n <= 0:
	        return 0
	      elif (n == 1):
	        return 1
	      else:
	        return fib(n-1) + fib(n-2)
	      
	  ```
	  #card
		- $O(N^2)$ . It can also be calculated using the earier formula $O(branches ^ depth). Since there are 2 branches and go as deep as N, it will be $O(2^N)$
		- Generally speaking when you see an algorithm with multiple recursive calls, you are looking at exponential runtime
	-
	- Big O Q12 : The following code calculates the fib numbers from 0 to n. What is the time complexity?
	  ```python
	  def allfib(n : int):
	  	for i in range(0,n):
	        print(f" {i} : {fib(i)}")
	        
	  def fib( n : int):
	  	if n <= 0:
	        return 0
	      elif (n == 1):
	        return 1
	      else:
	        return fib(n-1) + fib(n-2)
	      
	  ```
	  #card
		- Execution is as below
		  ${2^1} = 2$
		  $2^2 =4$
		  $2^3 = 8$...$2^n$
		- the sum of these is $2^{n+1}$. Hence it is $O(2^n)$
		-
	- Big O : Q13 : What is the technique of memoization? Can you write an algorithm for calculating fib series using memoization? #card
		- Memoization is a technique in which the previously computed values are remembered for using memory and later used as needed
		- ```python
		  def get_fibonacci_series(n: int) -> list[int]:
		      # Edge case: for n = 0, return just [0]
		      if n == 0:
		          return [0]
		          
		      # Initialize the list with base cases
		      fib_series = [0] * (n + 1)
		      fib_series[0] = 0
		      fib_series[1] = 1
		      
		      # Fill the array sequentially (Bottom-Up Memoization)
		      for i in range(2, n + 1):
		          fib_series[i] = fib_series[i - 1] + fib_series[i - 2]
		          
		      return fib_series
		  
		  # Example Usage:
		  n = 10
		  result = get_fibonacci_series(n)
		  print(f"Fibonacci series up to index {n}: {result}")
		  print(f"The {n}th Fibonacci number is: {result[n]}")
		  ```
		- Ignore the below code. Its advanced python feature. Noted here for reference only
		- ```python
		  from functools import lru_cache
		  
		  # maxsize=None allocates unlimited cache memory
		  @lru_cache(maxsize=None)
		  def fib_memo(n: int) -> int:
		      if n < 2:
		          return n
		      return fib_memo(n - 1) + fib_memo(n - 2)
		  
		  # Generate series up to index 10
		  fib_series = [fib_memo(i) for i in range(11)]
		  print(fib_series)
		  ```
	-
	- Big O : Q14 : The following code computes the product of a and b. What is its runtime? 
	  ```python
	  def product(a : int , b: int) -> int :
	    sum : int = 0
	    for i in range(0, b):
	      sum += a
	    return sum
	  ```
	  #card
		-
	- Big O: Q15 : The following code computes $a^b$. What is its runtime ?
	  ```python
	  def power(a : int , b:int) :
	    if b < 0:
	      return 0 #error
	    elif b == 0:
	      return 1
	    else:
	      return a * power(a, b - 1)
	  ```
	  #card
		-
	- Big O : Q16: The following code computes a % b. What is its runtime?
	  ```python
	  def mod(a : int , b: int):
	    if b <= 0:
	      return -1
	    div : int = a /b
	    return a - div * b
	  
	  ```
	-