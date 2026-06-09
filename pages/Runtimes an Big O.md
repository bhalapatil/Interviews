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
-