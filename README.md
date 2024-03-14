# Code_Analyzer

This repository is a simplified version of a first step in compiling a code - code analysis. The analysis is divided in three steps. 
1. Lexical analysis
2. Syntax analysis
3. Semantic analysis

In order to simplify the code, each step is divided in a separate program. Note that sometimes the processess are intertwined in order to increase efficiency.   

## Lexical analysis
The analyzer accepts a simple programming laguage that contains the followng lexical units:
1. keywords
  for - start of a for loop (KW_FOR)
  rof - closing a for loop (KW_ROF)
  from - start of a range (KW_FROM)
  to - end of a range (KW_TO)

2. variables/identifiers (IDN)

3. operators + (OP_ADD), - (OP_SUB), * (OP_MUPLTIPLY), / (OP_DIVIDE), ( (LEFT_P), ) (RIGHT_P), = (OP_ASSIGN)

4. constants (only integers for simplicity) (NUM)

The keywords that are written in the output of a program for each unit are written in parenthesis.
The program reads each line of users input and parses each lexical unit. For each unit it prints out the name of a unit, line number and the unit itself.   
For example:  
*a = 3  
b = 4*

will result in:  

*ID 1 a  
OP_ASSIGN 1 =  
num 1 3  
ID 2 b  
OP_ASSIGN 2 =  
NUM 2 4*

The program splits user input by lines and each line by space since it is the most common way of writing code. However, since compilers usually ignore whitespaces, this analyzer is also adjusted for inputs that don't contain whitespaces. That's why input such as "1abc" will not raise an error, even though variable names cannot begin with a numbers. It will be interpreted as a number "1" and a variable "abc" written without a space in between. Newlines are preserved even though they are ignored. In case of an error in later phases of analysis it is important to let the user know exactly which line caused an error.  

## Syntax analysis  

The program takes output of a Lexical Analyzer (LexicalAnalyzer.py) and returns a syntax tree. The rules are defined in patterns variable in the code. Since this is only a simplified version, it does not recover from mistakes. Therefore, if there is a mistake in code, the program is immediately terminated and the user is not notified of any other mistakes in the code.   
Note that '⏊' is a character that represents the end of input and '$' means that the following syntax unit is empty.   

## Semantic analysis  
... in progress ...
