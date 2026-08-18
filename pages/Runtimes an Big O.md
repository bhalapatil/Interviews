- What is time complexity ? #card
  card-last-interval:: -1
  card-repeats:: 1
  card-ease-factor:: 2.5
  card-next-schedule:: 2026-06-09T18:30:00.000Z
  card-last-reviewed:: 2026-06-09T13:06:21.953Z
  card-last-score:: 1
  id:: 6a26228c-0fb4-4d72-a358-6c9956c4ef1e
	- This means the time or # of steps an algorithm takes to complete given an input size of N. Some example of this is are O(N) , O(log N), $O(N^2)$ , O(N logN) etc
	- You can also have multiple variables in the runtime. For ex, to paint a fene that is w metres wide and h meters height, could be described as O(wh). If the paint is p layers then it is O(pwh)
- What are Big O , Big Theta and Big Omega ? #card
  card-last-interval:: 4
  card-repeats:: 1
  card-ease-factor:: 2.6
  card-last-reviewed:: 2026-06-09T13:07:29.983Z
  card-next-schedule:: 2026-06-13T13:07:29.982Z
  card-last-score:: 5
  id:: 6a2623f5-c621-4034-be75-361e23960dae
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
  id:: 6a2626d0-c779-42c8-92c2-18dc254542a4
	- Best Case : If all elements are equal, then quick sort will, on average, just traverse through the array once.
	-
- What is space complexity? #card
  card-last-interval:: 4
  card-repeats:: 1
  card-ease-factor:: 2.6
  card-last-reviewed:: 2026-06-09T13:08:54.510Z
  card-next-schedule:: 2026-06-13T13:08:54.510Z
  card-last-score:: 5
  id:: 6a26af3d-f7bb-4208-8ef1-54f6cf311783
	- Space complexity is the amount of memory (space) that is needed to execute the algorithm
- What is the space and time complexity of the below code? 
  card-last-interval:: 4
  card-repeats:: 1
  card-ease-factor:: 2.6
  card-last-reviewed:: 2026-06-09T13:09:30.908Z
  card-next-schedule:: 2026-06-13T13:09:30.908Z
  card-last-score:: 5
  id:: 6a26af62-a6dd-45a4-a35d-cdc79a190870
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
  id:: 6a26b033-85fb-4b5e-883f-98f3c797c1b5
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
  id:: 6a26b11b-3c0a-43dc-8f2b-1c85aaf98741
	- During the analysis the O(2N) will be changed to O(N). This is done because N is assumed to be sufficiently large.
- What is the runtime for the below code? 
  card-last-interval:: -1
  card-repeats:: 1
  card-ease-factor:: 2.5
  card-last-reviewed:: 2026-06-09T13:08:33.254Z
  card-next-schedule:: 2026-06-09T18:30:00.000Z
  card-last-score:: 1
  id:: 6a26b1d8-c2ff-4eb9-80c5-c9b426583acf
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
  id:: 6a26b3da-4715-49d8-81d3-db3a2b3d6bca
	- The factor  that has the highest exponent and ignore the rest. This is done because as N grows large the contribution of the non-dominant factors start becoming smaller and smaller compared to the dominant factor
-
- In which case should you add the runtimes and in which case you should multiple the,?
  card-last-interval:: 4
  card-repeats:: 1
  card-ease-factor:: 2.6
  card-next-schedule:: 2026-06-13T13:05:44.254Z
  card-last-reviewed:: 2026-06-09T13:05:44.254Z
  card-last-score:: 5
  id:: 6a2766ff-123e-46d0-aece-2108501b8730
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
		  id:: 6a276f60-aa46-496c-8c76-c24246bed483
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
	  id:: 6a277473-fe8e-4146-8c8a-834acdc0c162
		- O(log N). In general if the number of elements in the problem space gets halved each time, that will likely be a O(log N) runtime
- # Recursive
	- What is the runtime(time complexity) and space complexity and of this code? #card
	  card-last-interval:: 4
	  card-repeats:: 1
	  card-ease-factor:: 2.6
	  card-next-schedule:: 2026-06-13T13:04:06.466Z
	  card-last-reviewed:: 2026-06-09T13:04:06.466Z
	  card-last-score:: 5
	  id:: 6a277547-b113-44cb-83cb-476426631808
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
	  id:: 6a2778d4-1541-4ac2-96f5-b84b690e4f20
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
	  id:: 6a28b6b1-5b1b-4429-a438-52ab2e430aab
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
	  id:: 6a28b7b2-b7e3-49a6-9d52-a407e5f01a51
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
	  id:: 6a2a0ae9-1936-4997-9f19-234839a071cc
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
	  id:: 6a2a0b13-b2fa-4087-88a9-bc538a01713a
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
	  id:: 6a2a16fb-c411-4da3-8f06-dcd0980a828d
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
	  id:: 6a2a17e4-5817-4a05-9997-5846cc089431
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
	  id:: 6a2a0b07-c249-425d-b72d-fe3ff4b779a7
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
	  id:: 6a2f6161-773b-4f2f-97b1-c82b46bb8a55
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
		- $O(N^2)$ . It can also be calculated using the earier formula $O(branches ^ {depth})$. Since there are 2 branches and go as deep as N, it will be $O(2^N)$
		- Generally speaking when you see an algorithm with multiple recursive calls, you are looking at exponential runtime
	-
	- Big O Q12 : The following code calculates the fib numbers from 0 to n. What is the time complexity?
	  id:: 6a2f8e2d-4d90-4a69-a338-66b26957dd4d
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
	  id:: 6a2f8f44-41d0-4e45-8831-a34a605b7909
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
	  id:: 6a2a19a3-dccf-4cda-ad01-233348a78ec6
	  ```python
	  def product(a : int , b: int) -> int :
	    sum : int = 0
	    for i in range(0, b):
	      sum += a
	    return sum
	  ```
	  #card
		- O(b)
	- Big O: Q15 : The following code computes $a^b$. What is its runtime ?
	  id:: 6a2fea8f-7453-48bf-b65e-382a45083c74
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
		- O(b) --check
	- Big O : Q16: The following code computes a % b. What is its runtime?
	  ```python
	  def mod(a : int , b: int):
	    if b <= 0:
	      return -1
	    div : int = a /b
	    return a - div * b
	  
	  ```
	- Big O: Q17 The following code performs Integer division. What is its runtime? 
	  id:: 6a2fec1b-d17c-453f-a3bc-ea86d3c10eec
	  ```python
	  def div(a : int , b:int):
	    count = 0 
	    sum = b
	    while sum <= a:
	      sum += b
	      count = count + 1
	    return count
	  ```
	  #card
		- O(a/b)
	- Big O Q 18: The following code computes the integer square root of a number. If the number is not a perfect square (there is no integer ), then it returns -1. It does this by successive guessing. If n is 100, it first guesses 50. Too high ? Try something lower - halfway between 1 and 50. What is its runtime ?
	  id:: 6a30b38e-4f5d-4146-8305-962c5ec2ad87
	  ```python
	  def sqrt(n : int):
	    return sqrt_helper(n , 1 , n)
	  
	  def sqrt_helper(n : int , min : int , max:int):
	    if (max < min):
	      return -1
	    guess : int = (min + max) / 2
	    if (guess * guess == n):
	      return guess
	    elif (guess * guess < n):
	      return sqrt_helper(n , guess + 1 , max) # try higher
	    else:
	      return sqrt_helper(n , min , guess -1)
	    
	   
	  ```
	  #card
		- O(log(n)). The algorithm is doing a binary search of the square root and hence lo
	-
	- BIG o : q 19 : Code to find out the sqrt. What is the runtime
	  id:: 6a3286c1-c7d4-43e0-b6bd-787abeac7581
	  ```python
	  int sqrt(n: int):
	    guess = 1
	    for i in range(1, n):
	      if guess * guess == n:
	        return guess
	      elif guess * guess > n:
	        break
	    return -1
	  ```
	  #card
		- O(sqrt(n)) : Since the loop terminates at a value greater than the sqrt of n
	- Big O : Q 20: If a binary search tree is not balanced, how long might it take (worst case) to find an element in it? #card
	  id:: 6a3288ff-865b-4d79-96c4-e4822bc33051
		- O(n) : The tree could be a straight tree and the element might be at the botton
	- Big O : Q 21: You are looking for a specific value in a binary tree, but the tree is not a binary search tree. What is the time complexity of this? #card
	  id:: 6a328956-d111-4505-a28d-dae9729cd1e9
		- O(n)
	- Big O : Q 22 : The following code sums the digits in a number. What is its runtime?
	  id:: 6a3289a0-38b8-4f9c-bbe2-085f17c7f485
	  ```python
	  def sumDigits(n : int):
	    sum = 0 
	    while(n > 0):
	      sum += n % 10;
	      n = n / 10 # integer division
	    return sum
	  ```
	  #card
		- O(log n). A number of d digits can have $10^d$ in value. So if $10^d = n$ then d = $\log_{10}n$
	- Big O Q 23: The following code computes the intersection (the number of elements in common) of two arrays. It assumes neither array has duplicates. It computes the intersection by sorting one array (array b) and then iterating through array a checking (via binary search) if each value is in b. What is its runtime ?
	  id:: 6a328b1e-226b-404c-846d-2c885c5ac7ee
	  ```python
	  def intersection(a : List[int] , b:List[int]):
	    mergesort(b)
	    intersect: int = 0
	    for i in range(0,len(a)):
	      if binary_search(b , a[i]):
	        intersect += 1
	    return intersect
	  ```
	  #card
		- O( b log b + a log b). First, we have to sort array b which takes O(b log b) time. Then for each element in a, we do binary search in O(log b) time. The second part takes O(a log b) time
		-