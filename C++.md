C++  
***We are playing with data.*** 

*************  
# Table of Contents

1. [Useful](#useful)
2. [Compiler&Linker](#compiler_linker)
3. [how_it_work](#how_it_work)
4. [Variables](#variables)
5. [Functions](#functions)
6. [Header_files](#header_files)
7. [Conditions_and_branches ](#conditions_and_branches)
8. [Loops](#loops)
9. [Control_Flow](#control_flow)
10. [Pointers](#pointers)
11. [References](#references)
12. [Classes](#classes)
13. [Class vs Structures](#class_vs_structures)
14. [Const](#Const )
15. [How_to_write_a_class](#how_to_write_a_class)
16. [Static_Cpp_Outside Class](#static_cpp_outside_class)
17. [Local_Static](#local_static)
18. 

*************
### Useful
  
* **#include **:library to use random number (can call rand())  
* **rand()%9** to call rand num between 1 and 9  
* **srand()**: truly rand with a seed as arg  
* **#include ** : to use time  
* **srand(time(0))**: seed the time to rand  
* **->**: It's to access a member function or a member variable or reference of an object through a pointer (with a regular variable or reference you would use . )  
  
*************************  
  
### Compiler_Linker  
  
* Compiler changer code to be understandable by machine  
* Linker connect data  
  
You can trick compiler by just giving him what he wants:  
  
> For example if the compiler wants a function we can just create a new file with this function, then include in our main file this file then call the function before main like that:  
void Log(int p);  
  
*****************  
  
### how_it_work
  
* Pre -processing :  
#include ... basically copy header files before your program  
**#include ** will make streaming fucntion like cout or cin available to use.  
  
> binaries, executable files  
> main function return int because return 0 if everything works  
  
****************  
  
### Variables  
  
We can use Long and short variables.  
We can use unsigned variables.  
char can be number or caracter.  
**sizeof(bool)** : give size of variable  
  
> int -> 4 bit  
bool -> 1 bit  
double -> 8 bit  
  
****************  
  
### Functions  
  
Function with return type:  
  
~~~cpp
type name (parameters)(){  
return type  
}  
~~~  
  
Function with no return type:  
(don't need return)  
~~~cpp
void name(parameters(){  
}  
~~~  
  
**parameters**: what has changed between blocs of code, between different uses of the function  
>Common task multiple time -> create a function  
  
We usually break up functions into Declaration and definition:  
**Declaration** -> header files  
**Definition** -> translation unit (.cpp files)  
  
*******************  
  
### Header_files  
  
They are used to declare varibales or functions that are used in multiple programs. They are not used to make definition of the function but just to say that this function exist.  
  
**#include "name.h"** ("" include file are relative to the current file and <> have to be in one of the compiling include path directories )  
  
**name.h**  
  
Exemple:  
~~~  
#pragma once // (declare only once,  
// to not include twice the same thing) (better)  
~~~  
or can :  
~~~  
#ifndef _LOG_H  
#define _LOG_H  
#endif (same effect than pragma once)  
  
void initLog();  
void Log(const char* message);  
~~~  
**********  
  
### Conditions_and_branches  
  
An if conditions is jumping to some part of memory  
  
> if statements would be avoid if you want a super fast code  
  
*Exemple* :  
~~~  
int x = 5;  
bool comparisonResult = x ==5;  
if (comparisonResult){  
}  
~~~  
  
> if the if statement is only one line of code you can not use {}  
  
To check if **a number/or a pointer is a valid value**, we can use an if statement, **if null will not go into the loop**:  
~~~  
if (x) { ==> equal to if (x! = null)  
"hello"}  
  
else if is equal to else{  
if {  
~~~  
  
**************  
  
### Loops  
  
* **For**  
~~~  
for (int i = 0; i<5; i++){  
}  
  
bool condition = true;  
for ( ; condition ; ){  
}  
  
for ( ; ; ){  
} endless loop  
~~~  
  
* **While**  
~~~  
while ( i <5 ){  
}  
  
~~~  
  
* DO  
~~~  
do{  
  
  
}while (i<5) : will be done at least one time  
~~~  
  
************  
  
### Control_Flow  
  
**Gives more control how loops run**  
  
**continue* : inside loop, skip to the next iteration of this loop or end loop  
~~~  
for (int i=5; i<5; i++){  
if (i %2 == 0)  
continue;  
}  
~~~  
**break** : inside loop or switch statement, get out of loop  
  
**return** : get out of the function  
  
***************  
  
### Pointers  
  
**Managing Memory**  
A memory in a computer is a long straight street with a start and end, and house along with numbers (bits in computers)  
  
**pointer** : an integer that stores a memory address (address where the house is, where the specific bit of memory is)  
  
**void*** : we don't care what type the pointer is  
~~~cpp  
void* ptr = nullptr; // (memory address 0)  
int var = 8;  
void* ptr = &var; // store the memory address  
// of var in ptr  
~~~  
**Types doesn't matter for ptr**, it matters for manipulation of memories, but types matters for ptr when you want to read from ptr  
  
**Read from pointer** :  
~~~  
int var = 8; //(stored on the stack)  
int* ptr = &var;  
*ptr = 10; // (access value of ptr, stored in a  
// memory address)  
~~~  
  
**Create a variable on the heat** :  
~~~cpp  
char* buffer = new char[8]; // (I want to allocate  
//some memory for me, asking for 8 bits of memory)  
memset( buffer, 0 , 8) // files 8 bit of memory  
//set to 0 (filles a block of memory with data)  
delete[] buffer; //( delete the memory used)  
~~~  
  
**Pointers are variables** :  
double pointer, ptr to ptr , variable storing memory adress pointing to an other variable stroing an another address that as the data  
  
**char** ptr** : a ptr to a ptr  
  
************  
  
### References  
  
**An extension of ptr**  
  
> pretty much the same things as ptrs  
  
**reference** : a way to reference an existing variable  
~~~  
int a =5;  
int& ref = a;  
~~~  
> we created an allias, this variable doesn't realy exist for the computer, it's just the same variable all the time.  
  
**Comparison With ptr**:  
*With Ptr* :  
~~~  
void Increment (int* value){  
(*value)++;  
}  
  
int main {  
int a =5;  
Increment(&a);  
}  
  
~~~  
*With reference* :  
~~~  
void Increment (int& value){  
value++;  
}  
  
int main {  
int a =5;  
Increment(a);  
}  
~~~  
  
> Synthax sugar, cleaner, simpler  
  
>You have to immedialtly initialize.  
  
>Once you declared a reference, you can not change what it's refering too  
  
********************  
  
### Classes  
  
**Object oriented programming**  
**Class** : put together data and fct  
~~~  
Class player{ (unique type, creating a new variable type)  
public:  
int x, y  
int speed;  
};  
~~~  
**visibility** : how visible is the stuff inside the class (default private)  
**public** : can access to this variable outside this class  
**method** : function of a class  
~~~  
Class player{  
public:  
int x, y  
int speed;  
void move (int xa, ya){  
x += xa *speed;  
y+=ya*speed;  
}  
~~~  
> Synthax sugar  
  
>They can't do anything than structures can't do.  
  
********************  
  
### Class_vs_Structures  
  
**A class is private by default.**  
**A struct is public by default.**  
  
> Struct exist in part to have compatibility with C.  
~~~  
Struct player{  
}  
~~~  
**When do I use struct** : usage: playing on data, structure that represente variable, like a vector class;  
~~~  
struct vec2{  
float x,y;  
void Add(const Vec2& other){  
x = other.x +x;  
y= other.y +y;  
}  
}  
~~~  
  
> Representing data in a structure, use struct.  
  
> I would never use inheritence with struct.  
  
*******************  
  
### Const  
  
**const** : variables declared with ‘const’ added become constants and cannot be altered by the program  
  
* *Simple use* :  
  
const int Constant1=96;  
const int * Constant2 : variable ptr to a cte int  
int const * Constant2: same  
int * const Constant3: cte ptr to a variable int  
int const * const Constant: cte cte  
  
* *Use of const in functions return* :  
  
The **const pointer to a variable** is useful for storage that can be changed in value but not in memory  
  
A **ptr to a const value** is useful for returning const strings and array from fcts which because they are implemented as ptrs, the prog will try to alter and crash. But you will know the error that the value was not suppose to be altered.  
  
* *In parameter passing* :  
  
void Subroutine4(big_structure_type const &Parameter1);  
which will cause the variable to be passed without copying but stop it from then being altered.  
  
* *Object oriented* :  
~~~  
class Class2{  
void Method1() const;  
int MemberVariable1;  
};  
~~~  
which will ban Method1 in Class2 from being anything which can attempt to alter any member variables in the object.  
  
****************  
  
### How_to_write_a_class  
  
see code LogClass.cpp in home/Dev  
  
**To be completed**  
  
****************  
  
### Static_Cpp_Outside_Class  
  
* **Static outside a class**  
  
**static int s_Variable** : this variable is going to be linked only internly in this translation unit. It's kind of saying the variable private to the linker.  
  
> It's only going to be visible inside this .cpp file and not another.  
  
> We can't have two global variable with the same name.  
  
> We can use: extern int s_Variable  
  
**When do I use static outside a class** : if we don't need variable to be global, always being static unless we need cross linking between translation unit  
  
* **Static inside a class**  
  
> They are like a namespace but in a class.  
  
**When do I have to use static inside a class** : a data to be shared accross class, replace global variable. A data to be shared with all instances  
It's like a global variable but where we know exactly where is it.  
  
>Organization sugar.  
  
**Static methods** :  
  
> Have to use static arguments.  
  
A static method doesn't have a class instence.  
  
**When do I use static method** : Static data, data that doesnt change between class instence but we want actually to use inside our class  
  
***********  
  
### Local_Static  
  
> Two parameters to look for variables: Live time of a variable / scope of the variable (where the variable can be use)  
  
**a static Local variable** : live time = the entire program / scop = limited inside this fct  
~~~ 
void Funtion(){  
static int i = 0 ;  
i++;  
std::cout <
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE5MjUzOTcyNzRdfQ==
-->