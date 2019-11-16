# lab13
CSE 1321L: Programming and Problem Solving I Lab 

 

Lab 13 

 

Multi-Dimensional Arrays 

 

 

Exercise #1: Develop a program that prints out the sum of each column of a two-dimensional array. The program defines method sumColumn() takes a two-dimensional array of integers and returns a single-dimensional array that stores the sum of columns of the passed array. The program main method prompts the user to enter a 3-by-4 array, prints out the array, and then calls method sumColumns(). Finally, it prints out the array retuned by method sumColumns(). Document your code, and organize and space the outputs properly as shown below.  C++ students: instead of asking the user for input, you must read it from a file.  See appendix for more information. 

 

Sample run 1: 

 

Enter a value: 9 

Enter a value: 1 

Enter a value: 2 

Enter a value: 4 

. 

. 

. 

Enter a value: 3 

 

The entered matrix: 

 9    1    2    4 

 2    2    8    0 

 3    3    3    3 

 

Sum of column 0 is 14  

Sum of column 1 is 6  

Sum of column 2 is 13 

Sum of column 3 is 7 

 

Sample run 2: 

 

[SIMILAR FORMAT OF INPUT ABOVE, BUT DIFFERENT NUMBERS] 

 

The entered matrix: 

 10   10   10   10 

 1    1    1    1 

 50   50   50   50 

 

Sum of column 0 is 61  

Sum of column 1 is 61  

Sum of column 2 is 61 

Sum of column 3 is 61 

 

 

Page Break
Exercise #2: Develop a program that prints out the location of the largest value in a two-dimensional array. The largest values may appear more than once in the array, so you must only print out the first instance. The program defines method locateLargest() that takes a two-dimensional array of integers and returns the location (row index and column index) of the first largest value as a single-dimensional array. The program main method prompts the user to enter a 3-by-4 matrix, prints out the matrix, and then calls method locateLargest(). Finally, it prints out the array returned by method locateLargest(). Document your code, and organize and space the outputs properly as shown below. 

 

Sample run 1: 

 

[SIMILAR FORMAT OF INPUT ABOVE, BUT DIFFERENT NUMBERS] 

 

The entered matrix: 

 9    1    2    4 

 2    11   18   20 

 3    20   3    12 

 

First largest value is located at row 1 and column 3 

 

Sample run 2: 

 

[SIMILAR FORMAT OF INPUT ABOVE, BUT DIFFERENT NUMBERS] 

 

The entered matrix: 

 19   11   22   44 

 29   51   81   20 

 23   90   45   90 

 

First largest value is located at row 2 and column 1 

 

Sample run 3: 

 

[SIMILAR FORMAT OF INPUT ABOVE, BUT DIFFERENT NUMBERS] 

 

The entered matrix: 

 89   11   22   44 

 29   51   80   20 

 33   10   45   10 

 

First largest value is located at row 0 and column 0 

 

 

Exercise #3: Develop a program (name it AddMatrices) that adds two matrices. The matrices must of the same size. The program defines method Addition() that takes two two-dimensional arrays of integers and returns their addition as a two-dimensional array. The program main method defines two 3-by-3 arrays of type integer. The method prompts the user to initialize the arrays. Then it calls method Addition(). Finally, it prints out the array retuned by method Addition(). Document your code, and organize and space the outputs properly as shown below. 

 

Sample run 1: 

 

Matrix A: 

 2    1    2 

 7    1    8 

 3    20   3 

 

 

Matrix B: 

 1    1    1 

 1    1    1 

 1    1    1 

 

A + B: 

 3    2    3 

 8    2    9 

 4    21   4 

 

Sample run 2: 

 

 

Matrix A: 

 2    2    2 

 2    2    2 

 2    2    2 

 

Matrix B: 

 2    2    2 

 2    2    2 

 2    2    2 

 

A + B: 

 4    4    4 

 4    4    4 

 4    4    4 

 

 

Instructions: 

 

1.  Programs must be working correctly. 

2.  Programs must be completed and checked before working the assignment. 

3.  Programs must be checked by the end of the designated lab session. 

 

Appendix – Referencing row or column length 

C# 

int[][] grid = new int[4][5]; 

 

To get the row length use arrayname.GetLength(0) 

E.g.: grid.GetLength(0) 

 

To get the column length use arrayname.GetLength(1) 

E.g.: grid.GetLength(1) 

 

 

Java: 

int[][] grid = new int[4][5]; 

 

To get the row length use arrayname.length 

E.g.: grid.length 

 

To get the column length use arrayname[0].length 

E.g.: grid[0].length 

 

 

Page Break
Appendix for C++ Students 

 

One of the most common (and simplest) file formats for storing data is “comma separated values” – or .csv files.  You can make these in Microsoft Excel or something even simpler like Notepad or TextEdit.  They look like this: 

 

1, 2, 3 

4, 5, 6 

7, 8, 9 

 

Each data element is separated from the others by comma; note that there’s no comma at the end of the line.   

 

You’ve probably used getline a lot now, but there’s a variation of it that you probably haven’t used.  If we pass it three parameters instead of two, the third represents the “delimiter” between the data elements which, in this case, is the comma.  However, getline gives us a string, not a number – so we have to convert it to a number using “stoi” (or “string to int”).  The code below reads from a file called “matrices.csv” which is located in the “Debug” folder of the project (so it can be found).  Note: make this file before coding. 

 

#include <iostream> 

#include <fstream> 

#include <string> 

 

using namespace std; 

void main() { 

 

// Create a filestream object – just like last lab. 

fstream fs; 

// Open the file for reading using “in”.  

fs.open("matrices.csv", fstream::in); 

// When we read in from a file, it's a string (s).  

// We have to convert that string to a number (i). 

string s; int i; int sum = 0; 

 

// While we can read a row/string from the file... continue processing each row 

 

while (getline(fs, s, ',')) {// Get the first string, reading up until a comma (1st) 

i = stoi(s); sum += i;// Convert it to an int and add to sum 

cout << i <<"|";// Print it out 

getline(fs, s, ',');// Get the next value, reading until a comma (2nd)  

i = stoi(s); sum += i;// Convert it to an int... 

cout << i << "|";// Print it out 

getline(fs, s);// Get the remainder of the string (3rd) 

i = stoi(s); sum += i;// Convert it to an int... 

cout << i << endl; 

} 

cout << sum << endl; 

// Close the file 

fs.close(); 

cin >> s; 

} 
