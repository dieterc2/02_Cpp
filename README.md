02_Cpp
======

Intro to C++, learning to do things you can already do in Java

Reading
=======

**C++ Programming** at WikiBooks.

All of the readings are free online, though note that the book is under constant revision. If something looks crazy, ask me about it.

I will lecture about this material in class. These readings are meant to be used in reviewing/studying.

1. Why our code is split into .h files and .cpp files: https://en.wikibooks.org/wiki/C%2B%2B_Programming/Programming_Languages/C%2B%2B/Code/File_Organization (6p)
2. What is the :: operator for? https://en.wikibooks.org/wiki/C%2B%2B_Programming/Programming_Languages/C%2B%2B/Code/Statements/Scope Stop at "unnamed namespace"
3. What does the compiler do? What does it NOT do? What does the pre-processor do? What does the linker do? https://en.wikibooks.org/wiki/C%2B%2B_Programming/Programming_Languages/C%2B%2B/Code/Compiler Stop at "Compile speed" (4p) https://en.wikibooks.org/wiki/C%2B%2B_Programming/Programming_Languages/C%2B%2B/Code/Compiler/Preprocessor (13p) https://en.wikibooks.org/wiki/C%2B%2B_Programming/Programming_Languages/C%2B%2B/Code/Compiler/Linker (4p)
4. Bitwise operators. https://en.wikibooks.org/wiki/C%2B%2B_Programming/Programming_Languages/C%2B%2B/Code/Statements/Variables/Operators#Bitwise_operators (2p)
5. Arrays, and the subscript operator. https://en.wikibooks.org/wiki/C%2B%2B_Programming/Programming_Languages/C%2B%2B/Code/Statements/Variables/Operators#Subscript_operator_.5B_.5D (5p)
6. Pointers. https://en.wikibooks.org/wiki/C%2B%2B_Programming/Programming_Languages/C%2B%2B/Code/Statements/Variables/Operators#address-of_operator_.26 and https://en.wikibooks.org/wiki/C%2B%2B_Programming/Programming_Languages/C%2B%2B/Code/Statements/Variables/Operators#Pointers.2C_Operator_.2A (9p) Skip the part about multi-dimensional arrays, and the part about pointers to functions.
7. Dynamic memory allocation. https://en.wikibooks.org/wiki/C%2B%2B_Programming/Programming_Languages/C%2B%2B/Code/Statements/Variables/Operators#Dynamic_memory_allocation (4p)

Homework
========

1. Fork this repo
3. Fill in the blanks in the main.cpp with code that produces the correct result. Read the comments to find out what they ought to do.
4. Be sure to `git commit` and `git push` often
5. Update this file with your documentation and the answers to questions.
6. When you are ready to turn in your homework, submit a pull request from your repo to mine.
7. Be sure to check the pull requests for my repo on github to make sure it worked, and that your work has been submitted.

Documentation
=========

For each of the following functions in main.cpp, tell me whether or not you think it is working in your submission.

1. prime - My implementation of this program seems to be working based on two resources. First, the tester class in provided in the main.cpp file outputs a success message to the console window, and second, I translated the code to java and ran it through eclipse, where it also worked well.
2. defix - My first trial of defix did not work, due to an off by one error when using the substr function. After fixing that, the tester class computed a success message, so I think this one runs smoothly and correctly.
3. sumSlice - This function was the only one I wrote that got a success message on the first try, so I did not have any problems with debugging it. I think my submission of this one is correct. 
4. square - This is another program that I cross-checked with a java program. The only reason I used java to check the program was speed, as using eclipse is much easier to spot errors for me.
5. listPrimes - I think that listPrimes is working correctly (as the tester program gives a success message), although I still do not fully understand the concept of putting in a pointer variable vs. a regular variable (I know the difference, though I would not know which to use on a case by case basis). I will ask a similar question for the last question of this homework.

Questions
=======

#### 1. In C++, the compiler compiles each .cpp file separately, without looking at the others. Explain why this leads to the need for .h files.
	The need for .h files stems from the concept of separating declarations and defintions of objects, functions, variables, etc... Because the compiler does not compile everything side by side (as in java), in C++, everything must be declared before a programmer uses it. The .h file is a quick and easy
	way to put all the decalarations in one file, so that when the #includes "a .h file" line comes to play, the .h file is copied into the .cpp file and the compiler can see all the declarations of the object. This is faster, and cleaner.

#### 2. Explain the individual roles of the preprocessor, the compiler, and the linker. What type of inputs do they take? What kind of outputs do they produce? What is the purpose of each?
	Preprocessor: Part of the compiler (or can be a separate program) that reviews the source code first and makes small changes or tweaks compiler options so as to translate the source code and make directives on how to interpret parts of that source code. 
	Compiler: Computer program that translates source code into machine code, which is language that computers deal in. The proccess of translation is called compilation.	
	Linker: The linker makes executable files from the machine code and fixes undefined symbols by locating the object that defines them. 

#### 3. What is a "pointer"?
	Pointers are variables that map to the actual value of the type that it points to, as opposed to non-pointer variables that map to the address of where the content is stored. Pointers can map to different types, though each pointer variable itself is relativley similar in memory size.

#### 4. If I have a variable declared as `int x`, how do I find out what memory address that variable is stored at?
	If you have a variable x, you can find the memory address by assigning a variable starting with an ampersands character to the original variable. Ex., x = &y.

#### 5. If I want a variable `p` that can store the address of an int, what type should I declare `p` to be?
	From my understanding of C++ variable assignment, 'p' should also be declared as an int. Although 'p' is only pointing to the memory location of the content ('p' should be '&p'), the content is still of type int, so the variable must be compatible with that data type. 

#### 6. Just like Java, C++ has a `new` command. But C++ also has a `delete` command that Java does not have. Why do we need `delete` in C++, but not in Java? What is `delete` good for?
	The delete command in C++ frees up the memory of a pointer, in that it releases the memory that was mapped to the pointer so that it can be used for other assignments. In java, this was done automatically by the java virtual machine for us, which determined when
	an object was unreachable by code and freed up memory space.

#### 7. What is one question about C++ that you would like me to explain in class?
	I would like to know why, in the sumSlice function, we returned a type int * as opposed to int. Does this just mean we returned a pointer with the actual content, or is this a syntax detail that C++ uses?