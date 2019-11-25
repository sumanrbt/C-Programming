# C-Programming
C Programming Tutorial

You are adviced to follow the tutprial in the following order 1.Basic

### 1. Basic
  ### This tuorial is based on http://www.cs.colby.edu/maxwell/courses/tutorials/maketutor/
  #### you need a gcc compiler installed before you can clone and run this program
  
Here we have three files:

1. hellomake.c

This is the main c file that we are going to run, this has a call to the function that is defined in hellofunc.c.
    
  2.hellofunc.c
  
  This contains the definition of the function that we are going to use in our hellomake.c
  
  3.hellomake.h
  
  This contains the declaration of the function that is defined in hellofunc.c
  

You need to clone this repository and by using the command line you can compile the code using the following line and run the executable
The following methods are ordered in increasing order of proper use of the Makefile feature

       # Method 1
          gcc -o output.exe hellomake.c hellofunc.c
          
          to use this you  should change #include<hellomake.h> to #include "hellomake.h"
          so that the compiler knows that the header file can be found within the same directory           as the c file.
  
      # Method 2

        Sometimes you may get an error like
        fatal error: hellomake.h: No such file or directory #include <hellomake.h> ^~~~~~~~~~~~~
        compilation terminated.
        The reason for this is the compiler is not told where exactly to fing the header file,           so you need to add -I. at the end of the compile code
        
        gcc -o ouput.exe hellomake.c hellofunc.c -I.
        
        
          
    # Method 3
      Using a Makefile
      Remember in the Makefile, before the gcc command, you need a tab (not equivalent spaces,         else the make command will not be happy)
      
    # Method 4 a better make file
      We need to make the Makefile better by using standard ways which will make the compilation process of large fies easier.
      This is given as Makefiles2, while compiling the code you need to rename this as Makefile and run make, 
      Note that:
      CC- the compiler that is used (gcc)
      CFLAGS - the list of flags to pass to the compilation command
      In the dependency list we have put the obgject files instead of the c files, so the       compiler knows that it has to convert all the .c files to .o files at the begining before making the executable output
      
      # Method 5
      CC=gcc
      CFLAS=-I.
      DEPS=hellomake.h
      OBJ= hellomake.o hellofunc.o // has all the object files
      %.o:%.c $(DEPS)
          $(CC) -c -o $@ $< $(CFLAGS)
       hellomake: hellomake.o hellofunc.o
          $(CC) -c hellomake hellomake.o hellofunc.o
      
     The new ly added thing is to:
     for all the files ending in .o, using all the .c files and all the DEPS
     do compile using the gcc compiler -c to generate the object file 
      
      We add anotherr macro DEPS which is the set of .h files on which the .c files depend.
      Then we add a rule (%.o) which means apply this to all the files ending in .o suffix
      Then we write the rule which says  -c days to generate the object file and -o $@ tells the compiler to put he ouput of the compilation to the folder named on the left side of the : and $< is the first item in the DEPS list, and finally the CFLAGS as defined above
      Instead of $< which is the first of the deendency list, we can use $^ which is the right side of the :.
      
      
      
      
      

