- What are the ascii range value for alphabets? #card
  id:: 6a899738-369d-46a4-adc4-da97ee388806
	- Upper Case (A- Z) 65 to 90
	- Lower case a-z : 97 to 122
- What is Caesar cipher? #card
  id:: 6a89979e-80b2-4144-be02-a1a2c8e14e0c
	- This is a cipher mechanism in which the alphabets are shifted by a certain number
- Write an algorithm for the caesar cipher given a string and a key #card
  id:: 4ecaa167-ead8-43eb-a512-990dd46fbef3
	- The algorithm can be summarized as below
	- The uppercase letter is considered one range and the lower case is considered another range
	- For each character in the string, check if its a upper or lower case alphabet.
	- If upper case then add the key value to the character. If the results i greater than 90 then do a mod of 90 and add 64 to bring it back into the range of the upper case
	- similarly for the lower case do a mod of 122 and add 96 if the result is greater than 122
	- convert the number back to the character
	- For other characters add the key value to the ascii value
	- Return the resulting string
- Write a python program to Implement the encryption of a string using Caesar cipher ? #card
  id:: 6a8997d0-001f-454c-b766-0fa4402aa3d7
	-