## Reading

[Python Regular Expressions Tutorial](https://www.datacamp.com/community/tutorials/python-regular-expression-tutorial)
Welcome back to regex!

Character(s) and what they do:

* . A period. Matches any single character except the newline character.

* ^ A caret. Matches a pattern at the start of the string.

*  \A Uppercase A. Matches only at the start of the string.

* $ Dollar sign. Matches the end of the string.

* \ZUppercase Z. Matches only at the end of the string.

* [ ]Matches the set of characters you specify within it.

* \ 
	* If the character following the backslash is a recognized escape character, then the special meaning of the term is taken.  
	*  Else the backslash () is treated like any other character and passed through.  
	* It can be used in front of all the metacharacters to remove their special meaning.

* \w Lowercase w. Matches any single letter, digit, or underscore.

* \W Uppercase W. Matches any character not part of `\w` (lowercase w).

* \s Lowercase s. Matches a single whitespace character like: space, newline, tab, return.

* \S Uppercase S. Matches any character not part of `\s` (lowercase s).

* \d Lowercase d. Matches decimal digit 0-9.

* \D Uppercase D. Matches any character that is not a decimal digit.

* \t Lowercase t. Matches tab.

* \n Lowercase n. Matches newline.

* \r Lowercase r. Matches return.

* \b Lowercase b. Matches only the beginning or end of the word.

* + Checks if the preceding character appears one or more times.

* * Checks if the preceding character appears zero or more times.

* ?
	*  Checks if the preceding character appears exactly zero or one time.  
	*  Specifies a non-greedy version of +, *

* { } Checks for an explicit number of times.

* ( ) Creates a group when performing matches.

* < > Creates a named group when performing matches.


[shutil](https://pymotw.com/3/shutil/)
High-level File Operations
Found in these docs are:
Copying files
Copying File Metadata
Working with Directory Trees
Finding Files
Archives
and File System space
This is the sort of website that I would bookmark and come back to when I need to utilize the code they provide. Less one that I'd write a bunch of notes on. 
## Additional Resources

### Videos

[Automation Ideas](https://www.youtube.com/watch?v=qbW6FRbaSl0&t=69s)
1. Automatically moving files
	1. Example: automatically move files from downloads to desired folder, keeps downloads cluter free
2. Automatically move and rename files
	1. Using same example: change the file name to what you want (by date maybe?)
3. Open youtube when your favorite youtuber uploads a video
	1. Could use this to open up to any website (like stocks)
4. Calculate compounding interest
	1. this is what programming is about at the start, a simple task that takes you a while to do 


Optional: [Automating Your Browser and Desktop Apps](https://www.youtube.com/watch?v=dZLyfbSQPXI)

## Bookmark and Review

[Watchdog](https://pythonhosted.org/watchdog/)