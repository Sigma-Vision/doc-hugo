# Coding Style SigmaVision

## Introduction
This document is the official documentation for the coding style to be used in every project from SigmaVision. This document may be shared and used as reference.



## Braces
### Braces Style :

Braces must be written in the Allman indentation style, which is this one :
```c
//Allman indentation
while(1)
{
    foo += bar;
}
```
The following indentation styles are not allowed :
```c
while(1){
    foo += bar;
}


while(1)
    {
    foo += bar;
    }

while(1)
{   foo += bar;
}

while(1)
{   foo += bar;}
```

### Braces Indentation :
Content between braces must be indented with 4 spaces. Tab characters are not allowed.

### Braces on one-liners :
Braces must be ommited when not needed. Here is an example :
```c
if (result % 2 == 1)
    return 1;
else
    return 0;
```
In case of braces being ommited, the else and if keywords should be on the same line, as seen on this example :
```c
if (found)
    return 1;
else if (retry)
    find();
else
    return 0;
```

## Documentation
### Language :
Comments should be written in English, and should not contain any spelling error.
### One-line Comments :
One-line comments must be as following :
```c
//Comment

/*Please avoid this as much as possible for one-line comments*/
```

### Multi-line Comments :
Regarding multi-line comments, comments delimiters must be on their own line. Content lines must start with ** and be aligned with the delimiters.
Here is an example :
```c
/*
** This is correct
*/

/**
** This is also correct, but this is a doxygen comment used for documentation.
*/
```

Here are examples of comments that need to be avoided : 
```c
/* This is incorrect
*/

/*
This is also incorrect
*/

/*
* This is also incorrect
*/
```

### Comment documentation :
When writing documentation with comments, it is necessary to use doxygen comments, as displayed in previous examples.

### Obvious :
Please do not document the obvious. Documentation should usually not be much longer than the code it documents.

### Style :
Use imperative and avoid repetitions while documenting.

##  Limitations

### Exports :
There must be no more than 10 functions per source file, and no more than 5 exported functions.
### Functions :
#### Arguments : 
There must be no more than 4 arguments to any function.
#### Body :
The body of a function should not have more than 25 lines, braces not included, unless a valid reason is provided.
#### Prototypes :
Any exported function must be properly prototyped. Functions that take no argument should be prototyped as having only the void argument. Every prototype should also contain both the return type and the argument types.
Here are examples of valid prototypes :
```c
int main(int argc,char** argv);

int find(void);
```

## Global Syntax
### Digraphs / Trigraphs :
Digraphs and trigraphs must not be used.
### goto :
The goto statement must not be used.
### asm :
The asm declaration must not be used.

## Declarations
There must be at most one declaration per line.
### Type : 
If the declared variable should not be able to have negative values, you must declare it as unsigned.
### Static arrays declaration :
Here is a summary of the rules to apply at the declaration of a static array :
```c
// Correct  
int  array[5] = { 0 };  
// Correct  
int  array[5] = { 1, 2, 3 };  
// Incorrect  
int  array[5] =  
{ 1, 2, 3 };  
// Correct  
int  array[2][2] = {  
{ 0, 0 },  //  
{ 0, 0 }  //  
};
```

## Do while :
The closing brace of the  do while  control structure MUST be on the same line as the  while  keyword.
Here is an example :
```c
int  var = 0;  
do  
{  
    ++var;  
}  while  (var < 10);
```

## For
Multiple statements may be used in the for structure, and may be separated by a comma (,).
HOWEVER, the comma operator is not allowed outside of the for structure !
Example :
```c
for  (int  i = 0; i < 8; i++, c++); // This is correct

int  a = puts("message"), 12; // This is not allowed
```

## Switches
### default :
Switches must contain a default statement, unless all cases are previously covered.
### Indentation :
Please abide by the following example for the indentation of switches : 
```c
switch(showers_per_week)
{
case 0:
    printf("You are disgusting");
    break;
case 7:
    printf("You are normal");
    break;
default:
    printf("Unknow number of showers per week");
    break;
}
```
### Padding :
You must not have any spaces between the label and the following colon (:).

## Preprocessor
### Include guards :
Header files MUST be protected against multiple inclusions.
You must use include guards such as these.
Please note that the protection guard's name must be the name of the file in capitals, followed by _H.
```c
#ifndef FOO_H  
#define FOO_H  
// Content of foo.h  
#endif // ! FOO_H
```
### #else and #endif :
#else and #endif should be followed by a one-liner comment documenting their use.

### Mark :
The preprocessor mark (#) must appear on the first column.

### Macros :
Macro call SHOULD NOT appear where function calls wouldn’t otherwise be appropriate. Technically  
speaking, macro calls SHOULD parse as function calls.
#### Parentheses
Macro arguments SHOULD be surrounded by parentheses, as such :
```c
#define MULT(X, Y) ((X) * (Y))
```

#### Variadic
Macros may be variadic.
#### Token
The preprocessor MUST NOT be used to split a token.

## Deadcode 
Delivered projects must not contain any deadcode. In order to differenciate deadcode from actual code, and be able to remove it, please use #if 0 and #endif in order to disable a part of code.

## File
### DOS :
The DOS used must be LF. The DOS CR+LF must not be used.

### Blank lines :
Delivered code must not contain blank lines at the end and beginning of files.

## Naming convention
### Snake case :
Camel case should not be used. Snake case should be used.
### Abbreviation :
Variable names should be abbreviated, as long as it does not hurt comprehension.
### Charset :
Variable names should belong to the following charset :
`[a-z][a-z0-9_]*`

### Protection guard :
As mentioned higher in the document, protection guard must have as name the name of the file in capitals, concatenated to _H.

### Macro :
Macro names must be in capitals.

### global :
Global variable identifiers (variable names in the global scope) when allowed/used MUST start with  g_.
```c
extern int  g_debug;
```


