# Reading

Todays reading is about reading and writing files in python which can be useful for data manipulation. We're also looking at exceptions and assertions, methods for error handling. Making it easier to control cases within our program and handle them accordingly.

[Read & Write Files in Python](https://realpython.com/read-write-files-python/)

In this tutorial we're gonna learn:  

* what makes up a file and why it's important  
* the basics of reading and writing files  
* basic scenarios of reading and writing files  

So what is a file?  
Files are used to store data.  
most file systems have three main parts:  

1. Header: metadata with contents of file such as it's name, size, type and more
2. Data: contents of the file
3. End of File(EOF): special character that indicates the end of the file

File Paths:  
File path is a string that represents the location of a file, it has three major parts: 

1. folder path: location of folder
2. file name: the name of the file
3. extension: end of the file path and prefaced by a period (.) to indicate what type of file it is. 

Opening and Closing a File in Python:  
Opening is done by invoking the open() built-in function  
open requires an argument of a path or a file name  
It's also important to properly close a file once you're done  

|Character|Meaning|
|:--------|------:|
|'r'|Open for reading(default)|
|'w'|Open for writing, truncating (overwriting) the file first|
|'rb' or 'wb'|Open in binary mode (read/write using byte data)|

There are three different categories of file objects:

* Text files
  * Most common file encountered
    * open('abc.txt)
    * open('abc.txt, 'r')
    * open('abc.txt, 'w')
  * open will return a TextIOWrapper file object:  

```py
    file = open('stuff.txt')
    type(file)
    <<class '_io.TextIOWrapper'>>
```

* Buffered Binary files
  * used for reading and writing binary files
* Raw Binary Files
  * Raw file type is not typically used. It can be used as a low-level building block for binary and text streams

### Reading And Writing Opened Files  

|Method|What it does|
|:-----|:------------|
|.read(size=-1)|Reads the file based on the number of size bytes.|
|.readline(size=-1)|Reads at most size number of characters from the line. This continues to the end of the line then wraps back around|
|.readlines()|Reads the remaining lines from the file object and returns them as a list|
|.write(string)|Writes a string to the file|
|.writelines(seq)|Writes the sequence to the file. No line endings are appended to each sequence item. So you have to ad the appropriate line endings|


### Values and Interpretations 

|Value|Interpretation|
|:---|:--------------|
|0x89| Magic number indicating that this is the start of a PNG|
|0x50 0x4E 0x47|PNG in ASCII|
|0x0D 0x0A| DOS style line ending \r\n|
|0x1A|DOS style EOF character|
|0x0A|Unix style line ending \n|


Don't re-invent the snake.  
Built-in libraries that might be of use:  

* wave: read/write WAV files
* aifc; read/write AIFF and AIFC files
* sunau: read/write Sun AU files
* tarfile: read/write tar archive files 
* zipfile: work with ZIP
* configparse: create/parse config files
* xml.etree.ElementTree: create/read XML based files
* msilib: read/write microsoft installer files
* plistlib: generate and parse Mac OS X .plist files  

Recap of the tutorial: 

* What a file is
* how to open/close files properly
* how to read/write files
* techniques when working with files
* libraries to work with common file types

[Exceptions in Python](https://realpython.com/python-exceptions/)

Exceptions versus syntax errors:  
syntax errors occur when the parse detects incorrect statements.  
Exception errors occur whenever syntactically correct python code throws an error.  

If you want to throw an error when a certain condition is met you can "raise" an error.  
raise Exception(f'x should not exceed 5. the value of x was {x}')

The AssertionError Exception  
Assert means that if a condition turns true it can continue executing the code, and if it turns false it throws an AssertionError

Try and Except:  
Means to try: this code: then except: run this code when there is an exception  

Exceptions hide all errors, so you should avoid bare except clauses.  
instead use specific exception classes to catch and handle conditions  

Key take aways: 

* try clause is executed up until the point where the first exception is encountered
* except clause should have an exception handler
* anticipate multiple exceptions and differentiate how the program should respond to them  
* avoid using bare except clauses  

Else clause: no exceptions: run this code.  

Finally: always run this code.  

Summary: 

* raise allows you to throw an exception at anytime 
* assert enables you to verify if a certain condition is met and throw an exception if it isn't
* in the try clause, all statements are executed until an exception is encountered
* except is used to cath and handle the exceptions that are encountered in the try clause
* else lets you code sections that should run only when no exceptions are encountered in the try clause
* finally enables you to execute sections of code that should always run, with or without any previously encountered exceptions.

## Videos

[Read & Write Files in Python - Companion Video](https://realpython.com/courses/reading-and-writing-files-python/)

Going to learn about: Reading and Writing Files in Python 

* Opening/closing a file 
  * opened with open statement taking a name or path as the argument and must be closed after use
    * file = open("file")
    * file.close()
  * you can use a try/finally block to ensure the file gets closed
  * you can also use the with open("filename") as file then code block within that, once the method is closed the file will be closed no matter what
* There is a pay wall for the following topics:
  * reading a file
  * writing a file
  * appending a file
  * locating a file
  * what exactly a file is
  * looking at contents of a file 

### Bookmark and Review

[Reading and Writing Files in Python Quiz](https://realpython.com/quizzes/read-write-files-python/)