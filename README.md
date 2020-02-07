# ECS140-HW3

For this assignment you will be parsing a simpler version of tinyAda ,called nanoAda, and translating code written in nanoAda into Java. You will be provided with  a parser specification written in SableCC. The SableCC (Links to an external site.) framework will create a parse tree that you can traverse using a visitor pattern. The framework comes with classes that you can easily extend in order to accomplish language translation tasks. 

0) (optional) Learn how to work with SableCC (Links to an external site.) : You won't submit anything from this part, hence, there are no points for it, but it will benefit you greatly if you start here. Work through this tutorial (Links to an external site.) referenced below. 

1) Symbol Tables: Using the SymbolEntry class from the last assignment as a starting point, implement symbol tables for scope and role analysis using the Java collections framework and Java generics. Feel free to modify, or even completely replace the SymbolEntry class with code of your own.  Note that the tutorial on SableCC (Links to an external site.) linked below predates generics in Java. You may take inspiration from that tutorial to the extent that it helps, but, realize that it is  insufficient for this assignment as presented. While you may use as much of the SymbolEntry class as you need, you may not use any of the SymbolTable class. You must build your own symbol tables and they must use the collection framework and Java generics. 

2) Semantic Analysis: Using your symbol tables from the first part, you will need to extend one of the provided SableCC (Links to an external site.) adapters to re-implement scope and role analysis with nanoAda.  Implement a visitor class called SemanticAnalysis that walks the parse tree and builds the symbol table. Note that since nanoAda is much simpler than tinyAda, there will be some differences here. For example, nanoAda does not support user defined types.  

3)  Code Generation: For this phase you want to, again, extend one of the provided SableCC (Links to an external site.) adapters to implement code generation in a class called CodeGeneration. You will generate a java source file with the same name as the input ada file, only with a .java extension. Your created java class will invoke the topmost procedure from main such that, when compiled, will execute the code implemented in the ada file.

4) Write nanoAda code: Finally, you must write some code in nanoAda and translate that code into java using your translator code from the first three parts. Start by writing a program primes.ada that computes all prime numbers between 1 and 100. When run, this program should simply print a comma delimited list of boolean values, represented by the integers zero and one, indicating whether the number in that position is prime or not. For example, the first few characters of the output would look like "0,1,1,0,1" to indicate that 2,3,5 are prime and 1,4 are not.  Now, write another program called pix.ada that computes pi(x), the number of primes less than or equal to x, for the numbers between 1 and 100. This program should output a comma delimited list of integers that are the values of pi(x). 

For this assignment you will be using Java packages and your code must reflect the package hierarchy defined by SableCC (Links to an external site.). Start by creating a working directory for your project. From within this directory, run the SableCC (Links to an external site.) jar on the provided grammar definition file. This will create a directory called nada.  All Java code that you write must be placed inside of this directory. Underneath the nada directory you will want to create a directory called visitors. All of your tree walker classes that extend SableCC (Links to an external site.) tree walkers will go in this directory. 

To compile the application from your working directory you only need specify the full path of the location of your nada.java file, e.g., 

javac nada/nada.java
To run your application from your working directory, again, you should specify the package path, e.g.

java nada.nada primes.ada
Submission details will be posted this weekend, of course, you will be submitting a jar file. Additional information regarding semantics and other things to think about will also be posted this weekend. I've posted the basic framework of the assignment now so that you may get started with the project as son as possible. Do not wait until the last minute with this project. A significant part of this project is related to understanding how SableCC (Links to an external site.) based translators are written and you won't have a working language to test your nanoAda code with until you complete the first three parts. 

I suggest that you start by following this tutorial (Links to an external site.) that will walk you through a similar project with an even smaller language, a variant of pascal, that is similar to nanoAda.

Note: The provided grammar may contain bugs. Please report anything that you think is inconsistent on Piazza. Unlike working with a recursive descent parser, working with parser generators means that small changes to the grammar can be quickly implemented and will have very little impact on your code. I will do my best to lock down any inconsistencies within the first few days.
