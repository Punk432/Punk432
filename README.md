Data SEGMENT
 Greet1 DB '123', 13, 10, '$' 
 Greet2 DB '456', 13, 10, '$' 
Data ENDS

ASSUME CS:Code, DS:Data

Code SEGMENT
Start:
 mov ax, Data 
 
 mov dx, OFFSET Greet1 
 mov ah, 9
 int 21h

 mov dx, OFFSET Greet2 
 mov ah, 9
 int 21h

 mov al, 0 
 mov ah, 4ch
 int 21h
Code ENDS

Stack_ SEGMENT STACK
 DB 100h DUP(?) 
Stack_ ENDS

END Start
