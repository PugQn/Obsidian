*There are several areas in Physics and Engineering where computer programs have to be developed that make use of sparse matrices.  A sparse matrix is an extremely large two-dimensional array of integer  numbers that has very few elements of interest and all the other elements are set to zero.*

*These matrices are sometimes too big to store in computer memory and are then represented by linked lists instead. It is common to have 1000000x1000000 matrices, however only a few thousand elements would be different than zero (usually very small floating point numbers can be rounded up to zero).*

*Each node in the list contains the following information:*
- row;
- column;
- matrix value at position \[row, column];
- pointer to next node in the list;

*Any element of the matrix where the value is zero does not have a node in the linked list. We will assume that sparse matrices are always square, i.e. max rows = max columns.*
### Question 1
*What is the largest 2dimensional array of integer numbers that you can create using your usual compiler? (to be answered when you get access to a computer)*

maxint x maxint. This is because the values held in the node for row and column are limited by the maximum number that can be held in an int.
```
main(){
    int array[2147483647][2147483647];
    }
```
The above is the largest square matrix the compiler will work with, which is the same as maxint squared.
### Question 2
*Discuss the conditions in which sparse matrices are better represented by linkedlists. (tip: how many bytes do you need to represent an element using arrays, and using linkedlists?)*

The problem with using an array is that even if there is nothing stored in the element (a zero value) the element will still take up space. A linked list is better as it skips all the zero values and only stores what is necessary.

### Question 3
*Find out how to represent a matrix and how to add two matrices.*

A Matrix is represented in a table like format. 

Adding matrices together is simply adding the elements in the same position. It can only be done when the matrices are the same dimensions.
### Question 4
