# fortran_input_reader
## About

Employing this module helps you parse inputs to a Fortran program better using an input file. This module was inspired from a similar feature in PACKMOL program but is written in way that can be adopted to any fortran program very easily.

## What is it, exactly?
In order to read a few variables in a fortran program, you do something like this:
```fortran
...
READ (5,*) AnInteger4
READ (5,*) AnInteger8
READ (5,*) AReal4
READ (5,*) AReal4
READ (5,*) AStringl00
...
```
The input must also be entered (in StdIn)/written (in a file) in the same order:
```text
...
4               !AnInteger4
8               !AnInteger8
4.0E0           !AReal4
8.0D0           !AReal4
'Some string'   !AString100
...
```

Using **fortran_input_reader** lets you enter the input in the following manner:
```text
...
  AString100 'Some string'
!Set integers
  AnInteger8 8 !interger of kind 8
  AnInteger4 4 !integer of kind 4
!Set real numbers
  AReal4 4.0E0
  AReal8 8.0D0 !integer of kind 8
!end here
...
```
Note that the variables in the input file can be "declared" in any order. In addition, the file can have comments and indentation for readability.

## How to adopt it to my code?

Please look into the file 'variable_module.f90' and it is quite self-explanatory. 

