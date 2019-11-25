# C-Programming
C Programming Tutorial

You are adviced to follow the tutprial in the following order 1.Basic

# 1. Basic
  # this tuorial is based on http://www.cs.colby.edu/maxwell/courses/tutorials/maketutor/
  #you need a gcc compiler installed before you can clone and run this program
  
Here we have three files:

1. hellomake.c
    This is the main c file that we are going to run, this has a call to the function that is defined in hellofunc.c.
2.hellofunc.c
  This contains the definition of the function that we are going to use in our hellomake.c
3.hellomake.h
  This contains the declaration of the function that is defined in hellofunc.c
  

You need to clone this repository and by using the command line you can compile the code using the following line and run the executable

       # Method 1
          gcc -o output.exe hellomake.c hellofunc.c
          
          to use this you  should change #include<hellomake.h> to #include "hellomake.h"
          so that the compiler knows that the header file can be found within the same directory as           the c file.
          


