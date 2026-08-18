- How to  create Strings in python? #card
  id:: 6a7da7a8-7412-4e16-9e5b-d4bef2a9d66c
	- In Python, strings are used to represent text data. You can create them by enclosing characters in various types of quotes:
		- **Single quotes:** `'Hello'` **Double quotes:** `"Hello"` **Triple quotes:** `'''Hello'''` or `"""Hello"""`. These are used for multiline strings.
	- **Example:**
	- ```
	  name = "Python"
	  multiline = """This is a
	  multiline string."""
	  ```
- Are strings in python mutable or immutable? #card
  id:: 6a7da7a8-c4fe-44ac-9e1a-7548530399a1
	- **Immutability:** Once a string is created, you cannot change its characters. Any modification creates a new string object. **Ordered Sequence:** Strings are ordered, meaning each character has a specific position (index) starting from 0.
- How to index the characters in the python string? #card
  id:: 6a7da7a8-b129-428c-b611-fdca7dab80da
	- using the str[index] format
- How to access individual characters using their position.? #card
  id:: 6a7da7a8-4a34-47ef-9e77-ca603032fb1c
	- `text` is the first character. `text[-1]` is the last character (negative indexing). The first character is also index 0. Other characters can be accessed using the index
-
- What is string slicing and how to use it? #card
  id:: 6a7dd54c-9541-42ec-b538-45f460cc77db
	- Extract a portion of a string using `[start:stop:step]`.
		- **start:** Inclusive beginning. **stop:** Exclusive end. **step:** The interval (default is 1).
	- **Examples:**
	- ```
	  text = "Python Pro"
	  print(text[0:6])   # Output: 'Python'
	  print(text[7:])    # Output: 'Pro'
	  print(text[::-1])  # Output: 'orP nohtyP' (Reversed)
	  ```
- How can you  iterate Over Strings? #card
  id:: 6a7da7a8-4f18-4f18-a9cf-2f5f25191fab
	- You can use a `for` loop to go through every character in a string.
	- **Example:**
	- ```
	  for char in "Dev":
	      print(char)
	  # Output:
	  # D
	  # e
	  # v
	  ```
- How do the builtin methods on the string work in python? #card
  id:: 6a7da7a8-44c7-409e-828b-c22f05450770
	- Python provides a vast set of methods. These methods return new values and do not change the original string.
- What are case manipulation methods available on python strings? Give an example for each of them? #card
  id:: 6a7dd5ff-b88d-4d5a-bc69-af47d762fddd
	- Case Manipulation
		- **capitalize():** Capitalizes the first character. `"hi".capitalize() -> "Hi"`
		- **casefold():** Stronger version of lower() for caseless matching. `"MARIO".casefold() -> "mario"`
		- **lower():** Converts all characters to lowercase. `"HI".lower() -> "hi"`
		- **upper():** Converts all characters to uppercase. `"hi".upper() -> "HI"`
		- **swapcase():** Swaps cases (Upper to lower and vice versa). `"PyThOn".swapcase() -> "pYtHoN"`
		- **title():** Capitalizes the first letter of each word. `"python guide".title() -> "Python Guide"`
- What are searching and finding methods available on python strings? Give an example for each of them? #card
  id:: 6a7dd636-1e53-49db-9041-d311f4333368
	- Searching and Finding
		- **count(sub):** Returns the number of times a substring appears. `"apple".count("p") -> 2`
		- **find(sub):** Returns the lowest index of substring, or -1 if not found. `"hello".find("e") -> 1`
		- **index(sub):** Like find(), but raises a `ValueError` if not found. `"hello".index("e") -> 1`
		- **rfind(sub):** Returns the highest index (searches from right). `"banana".rfind("a") -> 5`
		- **rindex(sub):** Highest index, raises error if not found. `"banana".rindex("a") -> 5`
		- **startswith(pre):** True if string starts with prefix. `"Python".startswith("Py") -> True`
		- **endswith(suf):** True if string ends with suffix. `"image.png".endswith(".png") -> True`
- What are Modifying and Cleaning methods available on python strings? Give an example for each of them? #card
  id:: 6a7da7a8-86f7-49bd-99fa-eb05def6f8f0
	- **strip():** Removes leading/trailing whitespace or characters. `" hi ".strip() -> "hi"`
	- **lstrip():** Removes whitespace from the left. `" hi".lstrip() -> "hi"`
	- **rstrip():** Removes whitespace from the right. `"hi ".rstrip() -> "hi"`
	- **replace(old, new):** Replaces occurrences of a substring. `"hi".replace("h", "b") -> "bi"`
	- **split(sep):** Splits string into a list based on separator. `"a,b,c".split(",") -> ["a", "b", "c"]`
	- **rsplit(sep):** Splits from the right. `"a,b,c".rsplit(",", 1) -> ["a,b", "c"]`
	- **join(iterable):** Joins elements of an iterable into one string. `"-".join(["a", "b"]) -> "a-b"`
	- **zfill(width):** Pads the left with zeros. `"7".zfill(3) -> "007"`
	- **expandtabs(n):** Replaces `\t` with spaces. `"a\tb".expandtabs(4) -> "a b"`
	- **partition(sep):** Splits into a 3-part tuple at first separator. `"a=b=c".partition("=") -> ("a", "=", "b=c")`
	- **rpartition(sep):** Splits at last separator. `"a=b=c".rpartition("=") -> ("a=b", "=", "c")`
	- **splitlines():** Splits at line breaks. `"a\nb".splitlines() -> ["a", "b"]`
	- **removeprefix(pre):** Removes a prefix (Python 3.9+). `"Mr. Smith".removeprefix("Mr. ") -> "Smith"`
	- **removesuffix(suf):** Removes a suffix (Python 3.9+). `"file.txt".removesuffix(".txt") -> "file"`
	-
- What are some of the functions that are available that check the content of the strings? #card
  id:: 6a7da7a8-5e41-431a-8972-473320f2ad8e
	- **isalnum():** True if all characters are alphanumeric. `"Python3".isalnum() -> True`
	- **isalpha():** True if all characters are letters. `"abc".isalpha() -> True`
	- **isascii():** True if all characters are ASCII. `"abc".isascii() -> True`
	- **isdecimal():** True if all characters are decimals (0-9). `"12".isdecimal() -> True`
	- **isdigit():** True if characters are digits (includes superscripts). `"12".isdigit() -> True`
	- **isnumeric():** True if numeric (includes fractions/Roman numerals). `"½".isnumeric() -> True`
	- **isidentifier():** True if string is a valid variable name. `"var_1".isidentifier() -> True`
	- **islower():** True if all characters are lowercase. `"abc".islower() -> True`
	- **isupper():** True if all characters are uppercase. `"ABC".isupper() -> True`
	- **istitle():** True if string follows title case. `"Hello World".istitle() -> True`
	- **isprintable():** True if all characters are printable. `"hi".isprintable() -> True`
	- **isspace():** True if string contains only whitespace. `" ".isspace() -> True`
- What functions are available for alignment and Formatting or strings in python? #card
  id:: 6a7da7a8-7190-4f43-8976-8026065c6816
	- **center(width):** Centers the string in a field of given width. `"hi".center(6, "-") -> "--hi--"`
	- **ljust(width):** Left-justifies the string. `"hi".ljust(5, "-") -> "hi----"`
	- **rjust(width):** Right-justifies the string. `"hi".rjust(5, "-") -> "----hi"`
	- **format():** Injects variables into placeholders `{}`. `"Hi {}".format("Bob") -> "Hi Bob"`
	- **format_map():** Uses a dictionary to format placeholders. `"{x}".format_map({'x': 10}) -> "10"`
- What functions are available for Encoding/Translation of characters on python string? #card
  id:: 6a7ddaa4-6c1e-43a7-a0f7-875970376eb5
	- **encode():** Returns an encoded version of the string as bytes. `"hi".encode() -> b'hi'`
	- **maketrans() / translate():** Used for character-by-character replacement. `table = str.maketrans("abc", "123"); "abc".translate(table) -> "123"`
- 6. String Formatting Techniques
	- **% Operator (Old):** Uses C-style placeholders. `"Hi %s" % name` **format() Method:** Uses curly braces. `"Hi {}".format(name)` **f-Strings (Modern):** Fastest and most readable. `f"Hi {name}"`
- 7. Review Questions
	-
	- What happens when `find()` does not find a substring, versus `index()`? #card
	  id:: 6a7da7a8-ad87-4fee-abc1-6f83d050898c
		- find returns -1 and index returns a value error
	- How do you reverse a string using a slicing operator? #card
	  id:: 6a7ddadb-f30a-4b04-8192-503a22d4c50d
		- ```python
		  s = "one"
		  x = s[::-1]
		  ```
	- Why is the following code an error: `s = "Hello"; s = "h"`?
	- Which boolean method should you use to check if a string is a valid Python variable name? #card
	  id:: 6a7ddb56-d2db-456e-bd3e-360b6e9a4414
		- `isidentifier()` method
	- What is the difference between `isdigit()`, `isdecimal()`, and `isnumeric()`?
	- How do you remove only the leading spaces from a string? #card
	  id:: 6a7ddb63-e425-4375-b051-19b7027dfb3b
		- lstrip()` method
	- Which string formatting method is generally preferred in modern Python code? #card
	  id:: 6a7ddb69-0c77-4cb2-8a1d-09ec484d11b0
		- `format()` method or f-strings
	-
-