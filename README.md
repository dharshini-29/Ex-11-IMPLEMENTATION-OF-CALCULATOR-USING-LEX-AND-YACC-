# Ex. No : 11	
# IMPLEMENTATION OF CALCULATOR USING LEX AND YACC 
## Register Number : 212223220017
## Date : 18/04/2024 

## AIM   
To implement a calculator using LEX and YACC.

## ALGORITHM
1.	Start the program.
2.	Write a program in the vi editor and save it with .l extension.
3.	In the lex program, write the translation rules for the various mathematical functions.
4.	Write a program in the vi editor and save it with .y extension.
5.	Compile the lex program with lex compiler to produce output file as lex.yy.c. eg $ lex filename.l
6.	Compile the yacc program with yacc compiler to produce output file as y.tab.c. eg $ yacc –d arith_id.y
7.	Compile these with the C compiler as gcc lex.yy.c y.tab.c
8.	Enter an expression as input and it is evaluated and the answer is displayed as output.

## PROGRAM
## exp11.l:
```
%{
#include"y.tab.h"
#include<math.h>
%}
%%
([0-9]+|([0-9]*\.[0-9]+)([eE][-+]?[0-9]+)?) {yylval.dval=atof(yytext);return
NUMBER;}
log |
LOG {return LOG;}
In {return nLOG;}
sin |
SIN {return SINE;}
cos |
COS {return COS;}
tan |
TAN {return TAN;}
mem {return MEM;}
[\t];
\$ return 0;
\n|. return yytext[0];
%%
```
## exp11.y:
```
%{
#include"y.tab.h"
#include<math.h>
%}
%%
([0-9]+|([0-9]*\.[0-9]+)([eE][-+]?[0-9]+)?) {yylval.dval=atof(yytext);return
NUMBER;}
log |
LOG {return LOG;}
In {return nLOG;}
sin |
SIN {return SINE;}
cos |
COS {return COS;}
tan |
TAN {return TAN;}
mem {return MEM;}
[\t];
\$ return 0;
\n|. return yytext[0];
%%
```
## OUTPUT 
![image](https://github.com/dharshini-29/19CS409-Compiler-Design-Lab/assets/147474632/cf7de043-00e2-4d7e-ab90-58a742582b36)

![image](https://github.com/dharshini-29/19CS409-Compiler-Design-Lab/assets/147474632/20a897b0-4365-4674-ac37-d18f0de822d4)

## RESULT
The calculator is implemented using LEX and YACC and the output is verified.
