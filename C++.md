C++  
***We are playing with data.*** 
This guide is based on a Youtube serie about C++ made by TheChernoProject. [Link to the video tutorial](https://www.youtube.com/watch?v=18c3MTX0PK0&list=PLlrATfBNZ98dudnM48yfGUldqGD0S4FFb)
*************  
# Table_of_Contents

1. [Useful](#useful)
2. [Compiler&Linker](#compiler_linker)
3. [how_it_works](#how_it_work)
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
14. [Const](#const )
15. [How_to_write_a_class](#how_to_write_a_class)
16. [Static_Cpp_Outside Class](#static_cpp_outside_class)
17. [Local_Static](#local_static)
18. [ENUMS](#enums)
19. [Constructor](#constructor)
20. [Destructor](#destructor)
21. [Inheritence](#inheritence)
22. [Virtual Fuctions](#virtual_fuctions)
23. [Interfaces_Pure_Virtual_Functions](#interfaces_pure_virtual_functions)
24. [Visibility](#visibility)
25. [Arrays](#arrays)
26. [Strings_in_cpp](#strings_in_cpp)
27. [String_Literals_in_Cpp](#string_literals_in_cpp)
28. [Mutable_keyword](#mutable_keyword)
29. [Constructor_Initializer_List](#constructor_initializer_list) 
30. [Ternary_Operators](#ternary_operators)
31. [Create_Instantiate_objects](#create_instantiate_objects)
32. [New_keyword](#new_keyword)
33. [Implicit_conversion_Explicit_keyword](#implicit_conversion_explicit_keyword)
34. [Operators_and_Operator_Overloading](#operators_and_operator_overloading)
35. [This_keyword](#this_keyword)
36. [Object_Lifetime](#object_lifetime)
37. [Smart_Pointers](#smart_pointers)
38. [Copying_and_Copy_Constructors](#copying_and_copy_constructors)
39. [Arrow_Operator](#arrow_operator)
40. [Dynamic_Arrays_std_vector](#dynamic_arrays_std_vector)
41. [Using_Libraries](#using_libraries) 
42. [Multiple_return_values](#multiple_return_values)
43. [Templates](#templates)
44. [Stack_vs_Heap_Memory](#stack_vs_heap_memory)
45. [Macros](#macros)


*************
### UsefulUsing_Libraries 
* **#include **:library to use random number (can call rand())  
* **rand()%9** to call rand num between 1 and 9  
* **srand()**: truly rand with a seed as arg  
* **#include ** : to use time  
* **srand(time(0))**: seed the time to rand  
  
   [TOC](#table_of_contents)
*************************  
  
### Compiler_Linker  
  
* Compiler changer code to be understandable by machine  
* Linker connect data  
  
You can trick compiler by just giving him what he wants:  
  
> For example if the compiler wants a function we can just create a new file with this function, then include in our main file this file then call the function before main like that:  
void Log(int p);  
  
   [TOC](#table_of_contents)
*****************  
  
### how_it_works
  
* Pre -processing :  
#include ... basically copy header files before your program  
**#include ** will make streaming fucntion like cout or cin available to use.  
  
> binaries, executable files  
> main function return int because return 0 if everything works  
  
   [TOC](#table_of_contents)
****************  
  
### Variables  
  
We can use Long and short variables.  
We can use unsigned variables.  
char can be number or caracter.  
**sizeof(bool)** : give size of variable  
  
> int -> 4 bit  
bool -> 1 bit  
double -> 8 bit  
  
   [TOC](#table_of_contents)
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
  
   [TOC](#table_of_contents)
   
*******************  
  
### Header_files  
  
They are used to declare varibales or functions that are used in multiple programs. They are not used to make definition of the function but just to say that this function exist.  
  
**#include "name.h"** ("" include file are relative to the current file and <> have to be in one of the compiling include path directories )  
  
**name.h**  
  
Exemple:  
~~~cpp  
#pragma once // (declare only once,  
// to not include twice the same thing) (better)  
~~~  
or can :  
~~~cpp  
#ifndef _LOG_H  
#define _LOG_H  
#endif (same effect than pragma once)  
  
void initLog();  
void Log(const char* message);  
~~~  

 [TOC](#table_of_contents)
**********  
  
### Conditions_and_branches  
  
An if conditions is jumping to some part of memory  
  
> if statements would be avoid if you want a super fast code  
  
*Exemple* :  
~~~cpp 
int x = 5;  
bool comparisonResult = x ==5;  
if (comparisonResult){  
}  
~~~  
  
> if the if statement is only one line of code you can not use {}  
  
To check if **a number/or a pointer is a valid value**, we can use an if statement, **if null will not go into the loop**:  
~~~cpp  
if (x) { // ==> equal to if (x! = null)  
"hello"}  
  
else if is equal to else{  
if {  
~~~  
   [TOC](#table_of_contents)
**************  
  
### Loops  
  
* **For**  
~~~cpp 
for (int i = 0; i<5; i++){  
}  
  
bool condition = true;  
for ( ; condition ; ){  
}  
  
for ( ; ; ){  
} endless loop  
~~~  
  
* **While**  
~~~cpp  
while ( i <5 ){  
}  
  
~~~  
  
* DO  
~~~cpp  
do{  
  
  
}while (i<5) : will be done at least one time  
~~~  
 [TOC](#table_of_contents)
  
************  
  
### Control_Flow  
  
**Gives more control how loops run**  
  
**continue* : inside loop, skip to the next iteration of this loop or end loop  
~~~cpp 
for (int i=5; i<5; i++){  
if (i %2 == 0)  
continue;  
}  
~~~  
**break** : inside loop or switch statement, get out of loop  
  
**return** : get out of the function  
  
   [TOC](#table_of_contents)
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
~~~cpp  
int var = 8; //(stored on the stack)  
int* ptr = &var; //change the memory address of ptr to the one of var
*ptr = 10; // (access value of ptr, stored in a  
// memory address)  
~~~  
  
**Create a variable on the heap** :  
~~~cpp  
char* buffer = new char[8]; // (I want to allocate  
//some memory for me, asking for 8 bits of memory)  
memset( buffer, 0 , 8) // files 8 bit of memory  
//set to 0 (filles a block of memory with data)  
delete[] buffer; //( delete the memory used)  
~~~  
  
**Pointers are variables** :  
double pointer, ptr to ptr , variable storing memory adress pointing to an other variable stroing an another address that as the data  

  >(*ref) is called de-reference  

**char** ptr** : a ptr to a ptr  
~~~cpp
int* m_X, *m_Y
~~~

   [TOC](#table_of_contents)
************  
  
### References  
  
**An extension of ptr**  
  
> pretty much the same things as ptrs  
  
**reference** : a way to reference an existing variable, it's an ***alias*** !  

~~~cpp  
int a =5;  
int& ref = a;  // ref = a so if we modifie ref we modifie a and if we modifie a we modifie ref
~~~  
> we created an allias, this variable doesn't realy exist for the computer, it's just the same variable all the time.  
  
**Comparison **:  
*With Ptr* :  
~~~cpp 
void Increment (int* value){  
(*value)++;  
}  
  
int main() {  
int a =5;  
Increment(&a);  
}  
  
~~~  
*With reference* :  
~~~cpp 
void Increment (int& value){  //It means : int& value = a; value has become a reference of a
value++;  
}  
  
int main() {  
int a = 5;
Increment(a);  
}  
~~~  
  
> Synthax sugar, cleaner, simpler  
  
>You have to immediately initialize.  
  
>Once you declared a reference, you can not change what it's refering too  

 > Always pass your object as const reference, at a basic level  !!!
  
   [TOC](#table_of_contents)
********************  
  
### Classes  
  
**Object oriented programming**  
**Class** : put together data and fct  
~~~cpp  
Class player{ (unique type, creating a new variable type)  
public:  
int x, y  
int speed;  
};  
~~~  
**visibility** : how visible is the stuff inside the class (default private)  
**public** : can access to this variable outside this class  
**method** : function of a class  
~~~cpp  
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
  
   [TOC](#table_of_contents)
********************  
  
### Class_vs_Structures  
  
**A class is private by default.**  
**A struct is public by default.**  
  
> Struct exist in part to have compatibility with C.  
~~~cpp  
struct player{  
}  
~~~  
**When do I use struct** : usage: playing on data, structure that represente variable, like a vector class;  
~~~cpp 
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
  
   [TOC](#table_of_contents)
*******************  
  
### Const  
  
**const** : variables declared with ‘const’ added become constants and cannot be altered by the program  
  
* *Simple use* :  
 
const int Constant1=96;  
const int*  Constant2 : variable ptr to a cte int , cannot modify the content of the ptr
int const* Constant2: same ( look the position of the ptr symbol*)
int* const Constant3: cte ptr to a variable int  
int const * const Constant: cte cte  

* *Use of const in functions return* :  
  
The **const pointer to a variable** is useful for storage that can be changed in value but not in memory  
  
A **ptr to a const value** is useful for returning const strings and array from fcts which because they are implemented as ptrs, the prog will try to alter and crash. But you will know the error that the value was not suppose to be altered.  
  
* *In parameter passing* :  
  
void Subroutine4(big_structure_type const &Parameter1);  
which will cause the variable to be passed without copying but stop it from then being altered.  
  
* *Object oriented* :  
~~~cpp 
class Class2{  
void Method1() const;  
int MemberVariable1;  
};  
~~~  
which will ban Method1 in Class2 from being anything which can attempt to alter any member variables in the object.  

Example:
~~~cpp
#include <iostream>
#include <string>

class Entity{
private:
	int m_X, m_Y;
public:
	int GetX() const // this method is not going to modify the class, any members variables, read only
	{
		return m_X;
	}
	// 
	const int* const GetX() const { //return a cte ptr that has a cte content that can not modifed the class
		return m_X
		}
	void SetX(int x){ // not const, because we write to the class
		m_X = x;
		}
};
void PrintEntity(const Entity& e){
	std::cout<< e.GetX()<< std::endl; //if I have a const ref in the argument, I can only call a const method.
	}
~~~
  
   [TOC](#table_of_contents)
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
  
   [TOC](#table_of_contents)
***********  
  
### Local_Static  
  
> Two parameters to look for variables: Live time of a variable / scope of the variable (where the variable can be use)  
  
**a static Local variable** : live time = the entire program / scop = limited inside this fct  
~~~cpp 
void Funtion(){  
	static int i = 0 ;  
	i++;  
	std::cout <<i<<std::endl;
	}
~~~
==  
~~~cpp
int i = 0 ;  
void Funtion(){  
	i++;  
	std::cout <<i<<std::endl;
	}
~~~
Example:  
~~~cpp
class Singleton{  
private:  
static Singleton* s_Instance;  
public:  
static Singleton& Get() { return *s_Instance;}  
void Hello(){}  
};  
Singleton* Singleton::s_Instance=nullPtr;  
int main(){  
Singleton::Get().Hello();  
}  
~~~  
==  
~~~cpp  
class Singleton{  
public:  
static Singleton& Get() {  
static Singleton instance;  
return *s_Instance;  
}  
void Hello(){}  
};  
  
int main(){  
Singleton::Get().Hello();  
}  
~~~

 [TOC](#table_of_contents)
***********  
  
### ENUMS  
  
**Enums** : a way to give a name to a value  
A way to name value  
> Helps to have a cleaner code  
  
Example :  
~~~cpp
enum Example : unisgned char { //int by default  
A = 0 ,B = 6 ,C = 8 //if not defined start from  
// 0 then increment 1 (A=0 , B=1,...)  
};  
int main {  
	Example value = B;  
	if (value ==1){  
	}
}
~~~

   [TOC](#table_of_contents)
*************  
  
### Constructor  
  
**Initialize a class**.  
  
A special type of method launched everytime we instanciated an object  
>Replace a void init()  
  
>A method that get called every time we construct an object  
  
~~~cpp 
Class Entity{  
public:  
	float X,Y  
	Entity() { // as to match the name of the class  
	}  
	Entity (float x, float y){  
		X=x;  
		Y=y;  
	} 
};
  
Entity e(10.0f,5.0.f);  
~~~  
  
>To delete the default constructor: Log() = delete;  

   [TOC](#table_of_contents)
****************  
  
### Destructor  
  
A special method gets called when an object get destroyed (for example when we get out of a fct loop)  
  
>Unitialize everything, opposite of the constructor, free memory  
  
~~~cpp  
~Entity() { // ~ to specify a destructor and not constructor  
}  
~~~  
  
   [TOC](#table_of_contents)
***************  
  
### Inheritence  
  
**inheritence** : allows base class contain basic functionnality then branch to have subclass from this parent class  
~~~cpp  
class Entity{  
public:  
	float X,Y;  
	void Move(float xa, float ya){  
		X=+ xa;  
		Y=+ya;  
		}  
};  
  
class Player : public Entity  
{  
public:  
	const char* name;  
};  
int main{  
	player.Move(5, 5);  
}  
~~~  
Player is a sub class of entity. It has the type player and entity.  
Playert has everything entity has.  
We can add informations that are not in entity in player.  
  
**Polymorphise**:  
We can also use Player everywhere we wanted to use Entity, because Player has everything from Entity + some specific stuff.  
Inheritence:  
  
> A way to extend an existing class, profide new functionnalities to a base class. Super class = Entity, base class  
  
   [TOC](#table_of_contents)
*************  
  
### Virtual_Fuctions  
  
**Virtual fuctions** : overwrite methods in subclass  
~~~cpp  
Class Entity{  
public:  
	std::string getName() { return "Entity";}  
};  
  
Class Player: public Entity{  
private:  
	std::string m_Name;  
public:  
	Player(const std::string& name)  
	: m_Name(name){}  
	std::string GetName() { return m_Name;}  
};  
void PrintName(Entity* entity){  
	std::cout >> entity->GetName() << std::endl;  
}  
int main()  
{  
	Entity* e = new Entity();  
	PrintName(e);  
	Player* p =new Player("Louis");  
	PrintName(p);  
	std::cin.get();  
}  
~~~  
Entity get print twice and not Louis .  
  
Because it go inside intity and call entity, it cause methods refer to the type.  
But we want the getName inside Player.  
Then we use virtual function, to overwrite the function in the base function and use the subclass function instead.  
~~~cpp 
Class Entity{  
public:  
	virtual std::string getName() { return "Entity";}  
};  
  
Class Player: public Entity{  
private:  
	std::string m_Name;  
public:  
	Player(const std::string& name)  
: m_Name(name){}  
	std::string GetName() override{ return m_Name;}  
};  
void PrintName(Entity* entity){  
	std::cout >> entity->GetName() << std::endl;  
}  
int main()  
{  
	Entity* e = new Entity();  
	PrintName(e);  
	Player* p =new Player("Louis");  
	PrintName(p);  
	std::cin.get();  
}  
~~~  
  
We add virtual in the base class in front of the fct name.  
We add override in then end of the name of the function that overwrite the fct in the base class. (c++11). (it's not a must but it helps for to make the code more clear and gives feedback on error in the name or else)  
  
**How does it work ?**  
Dynamic dispach using V-table, mapping for all the virtual function inside the base class to map them to the overwrite function.  
  
>Additional memory use when using virtual function.  
  
>Go trough the table to map the function.  
  
>The impact is still minimal.  
  
   [TOC](#table_of_contents)
   
*****************  
  
### Interfaces_Pure_Virtual_Functions
  
Allow us to define a function in a base class, that does not have an implementation and force subclass to implement that fct.  
  
We want to force the subclass to provide its own definition.  
  
It s commun to do a base class full of undefined methods and force the subclass to implement them, it's called an interface, a class that only consist on unimplemented methods, acting like a template.  
  
> It's not possible to instentiate that class. (Instentiate = Entity entity)  
  
~~~cpp  
virtual std:string getName() = 0; // =0 make a pure virtual fct that has to  
// be implemented in an another fct  
~~~  
~~~cpp  
Class Printable{  
public:  
	virtual std::string GetClassName() =0;  
};  
  
Class Entity : public Printable {  
public:  
	virtual std::string getName() { return "Entity";}  
	std::string GetClassName() {return "Entiry";}  
};  
  
Class Player: public Entity{  
private:  
	std::string m_Name;  
public:  
	Player(const std::string& name)  
: m_Name(name){}  
	std::string GetName() override { return m_Name;}  
	std::string GetClassName() {return "Player";}  
};  
void PrintName(Entity* entity){  
	std::cout >> entity->GetName() << std::endl;  
}  
  
void Print( Printable* obj){  
	std::cout << Entity->getName() << std::endl;  
}  
  
int main()  
{  
	Entity* e = new Entity();  
	Player* p =new Player("Louis");  
	Print(e);  
	Print(p);  
	std::cin.get();  
}  
  
~~~  
  
> There is no interface keyworld in C++, it's just a class.  
  
   [TOC](#table_of_contents)
*******************  
  
### Visibility

Object oriented programming.
**How visible members or methods are visible, who can see them, who can use them.**
>No effect on program performance, right better code.
Organization sugar.

Private, Protected, Public.
*Private* : 
~~~cpp
class Entity{
private: //only this Entity class can access this variable, read and write. 
	int X, Y;
};
~~~
friend can access private variable.
 
*Protected* :
~~~cpp
class Entity{
protected: //only this Entity class can access this variable, read and write. 
	int X, Y;
};
~~~
More visible than private, but less than public. This class and the subclass can access variables and methods, but not outside the class, for example inside the main. 

*Public* :
~~~cpp
class Entity{
public: //only this Entity class can access this variable, read and write. 
	int X, Y;
};
~~~
Everyone can access, class, subclass and outside.

Private tells you shouldn't be accessing this outside the class. It helps you understand a code.
We can ensure that people don't break things, called something than his not supposed to be called.

 [TOC](#table_of_contents)
***************

### Arrays

A collection of elements, a way to represent a collection of variables.

> Having multiple variables inside a single variable.

> Start with 0 in C++

~~~cpp
int main{
	int example[5];	
	example[0] =2;
	example[4] =4;
}
~~~
If you have an index problem (**memory access violation**), writing outside the bounds of the array, you will have memory address, you will access memory that don't belong to your array variable.
Always write in the bounds of your array, **hard to debug**, you have write in memory that you don't know may be in another variable memory.

> For loop is a good way to go through the entire array. 

Memory: you have 4 segments of 4 bits (int = 4 bit)  each in the example above, one after another in a row.

An array is an integer pointer to the block of memory that contains the 4 integers. 
~~~cpp
int main{
	int example[5];	
	int* ptr = example;
	example[2] =5;
	*(ptr + 2) = 5; // same meaning of the line above but takes more bits 
	*(int*)((char*)ptr + 8) = 5; //same meaning, with same bits
}
~~~
> When we are doing ptr arithmetic, in term of bits, the numbers of bits he is going to add depend on the type. For example, above we are going to add two times 4 bits because it's integer. 

*Array on the heap* 
~~~cpp
int main{
	int example[5]; //will be deleted at the end of main	
	int* another = new int[5]; //needs to be manualy deleted using delete keyword (delete[])
	for	(int i=0, i<5,, i++){
		example[i] = 2;
		anotger[i] = 2; 
		}
	delete[] another;
}	
~~~
Why dynamically allocate in the heap ?
Lifetime. 
But It takes a lot of performance.

~~~cpp
int count = sizeof(example) / sizeof(int); //to know the size of the array only on the stack
~~~
Not very beautiful and not very trust-able. 

*Other way* :
~~~cpp
class Entity{
public:
	static const int exampleSize = 5;
	int example[exampleSize]; //has to a compile time known const = static const
	Entity()
	{
		for (int i =0; i<exampleSize; i++)
			example[i] = 2;
	}
};
~~~
*In C++ 11* :
~~~cpp
class Entity{
public:
	std::array<int, 5> example; //type,size
	
	Entity()
	{
		for (int i =0; i<example.size(); i++)
			example[i] = 2;
	}
};
~~~

It's worth it to use c++11 array usually. It's safer because it maintained size. 
>They are called standard array and int array[5] are called raw array.

 [TOC](#table_of_contents)
 
***********

### Strings_in_cpp

An array of characters.
~~~cpp
int main{
	const char* name = "Louis"; //we can not change the content with const
	char name[5]= { 'L', 'o', 'u','i', 's',0} //equal to the line above
	}
~~~
ASCII representation in memory.
A string always ends with a 00 bit in memory. That's how the computer now, where the string end. 

*In C++*:
~~~cpp
#include <string>
int main{
	std::string name = "Louis";
	std::string name = std::string("Louis") + "Hello"; //adding strings
	bool contains = name.find("lo") != std::string::npos; //npos position
	name.size();
	}
~~~

You should use the std string library. 
***" string "*** : (double quote) means const char array.

~~~cpp

void PrintString(std::string string){
//Here we are copying string, thats very slow.
	std::cout << string << std::endl;
	}
void PrintString(const std::string& string){
//.Reference = won't be copied, const = means we promise not changing the string
	std::cout << string << std::endl;
	}
~~~
String copying is very slow, try to avoid.

 [TOC](#table_of_contents)
 
 ****************
### String_Literals_in_Cpp

***String Literals*** = "Louis" 
~~~cpp
	const char* name ="Louis"; // const remind you that you never modified a string defined 				like this
	const wchar_t* name2 = L"Louis"; //Wide characters
	const char16_t* name3 = u"Louis"; //UTF 16
	const char32_t* name4 = U"Louis"; //UTF 32
~~~
*string_literals library*:
~~~cpp
	using namespace std::string_literals; //c++14, you can put symbol in front or end of "" 
	std::wstring name0 = u8"Louis"s + U"Hello"; //the s at the end mean stand string
	const char* example = R"(Line1 //multi lines strings, R stands for roll
	Line2
	Line3
	Line4)";
~~~

 [TOC](#table_of_contents)
 
*****************
### Mutable_keyword 

*mutable with const*:
Can be change. 
~~~cpp
class Entity{
private:
	std::string m_Name;
	mutable int m_DebugCount = 0;
public:
	const std::string& GetName() const
	{
		m_DebugCount++;
		return m_Name;
	}
};
int main{
	Entity e;
	e.GetName();
	}
~~~

*mutable with lambda*:
a lambda is a throw away fct. 
~~~cpp
int main{
	Entity e;
	e.GetName();
	
	int x = 8;
	auto f = [=]() mutable //ref = & value = = 
	{	
		x++
		std::cout << x << std::endl;
	};
	f();
}
~~~

> it's very rare to use mutable in a lambda fct, it's not a common case. 

 [TOC](#table_of_contents)

**************

### Constructor_Initializer_List 
(Member initialiser list) 
It's a way to initialize our class members fct in the constructors.

~~~cpp
class Entity{
private:
	int m_score;
	std::string m_Name;
public:
	Entity() 
		: m_score(0), m_Name("Unknown") //member initializer list, in the same order that your declare the members
	{
		// m_Name ="Unknown"; //we can delete this now this we initialize above
		}
	Entity (const std::string& name)
		:m_Name(name)
		{	
		// m_Name = name;
		}
	const std::string& GetName() const
	{
		return m_Name;
	}
};
int main{
	Entity e;
	e.GetName();
	}
~~~
There is a difference of performance, using member initialiser list is more performante because when you don't  you create one initialization with the default constructor and one with the actual constructor. See the example done here:

Example: 

~~~cpp
class Example{
public:
	Example() 
		: m_Name("Unknown") 
		{	
		std::cout<< "Created Entity!" << std::endl;
		}
	Example(int x)
	{
		std::cout<< "Created Entity with " << x <<  std::endl;
		} 
	const std::string& GetName() const
		: m_Name(name)
	{
	}
};
class Entity{
private:
	Example m_Example; // create an Example here, that will be thrown away
	std::string m_Name;
public:
	Entity()
		: m_Example(8) //or m_Example(Example(8)) // with this we created only one entity
	{
		// m_Example = Example(8); //and here so we have two object instead of one
		}
	Entity (const std::string& name)
		:m_Name(name)
		{	
		}
};
int main{
	Entity e;
	}
~~~
>It's not only a matter of style, it actually make the code more performante !
Should use this all the time !!!!

 [TOC](#table_of_contents)

*************

### Ternary_Operators

***? :*** -> ***Syntactic sugar*** for If statements
> If statement in one line !

~~~cpp
static int s_level = 1;
static int s_Speed = 2;
int main{
	if (s_Level >5)
		s_Speed = 10;
	else
		s_Speed = 5;
}
~~~
==
~~~cpp
static int s_level = 1;
static int s_Speed = 2;
int main{
		s_Speed = s_Level >5 ? s_Level > 10 ? 15: 10 : 5; //conditions true ? yes : no 
		s_Speed s_Level > 5 ? 15: 10 : 5;
}
~~~

> If there is multiple statements don't use ternary operator, it get confusing. 


 [TOC](#table_of_contents)

*****

### Create_Instantiate_objects

>Stack and Heap are the two main memories allocation in C++ 

*Instantiate object* :
~~~cpp
class Entity{
private:
	std::string m_Name;
public:
	Entity () : m_Name ("Unknown"){}
	Entity (const std::string& name)
		:m_Name(name){}
	const std::string& GetName() const { return m_Name;}
};
int main{
	Entity e; //Instantiate on the stack Object/Name
	Entity e("Louis"); // with a parameters
	Entity e = Entity("Louis"); //same as line above
	e.GetName(); 
	}
~~~
It' s the fastest way to instantiate in C++, if you can al ways do it like the example above. 

*Instantiate on the heap*:
Why ?
* if we want that the object to live after a scoop end, for example outside a fonction where we instantiate our object
* Not enough memory in the stack.
~~~cpp
class Entity{
private:
	std::string m_Name;
public:
	Entity () : m_Name ("Unknown"){}
	Entity (const std::string& name)
		:m_Name(name){}
	const std::string& GetName() const { return m_Name;}
};
int main{
	Entity* e;
	{ //empty {}
		Entity* entity = new Entity e("Louis"); //new allocate on the heap
		e = entity;
		e.GetName();
	}
}
~~~
 >Allocates on the heap takes longer than allocates on the stack, performance is slower on the heap than stack
 You have to free manually the memory on the heap (with delete entity;)

> Always create on the stack unless you can't !

> Stack is usually 1MB 

 [TOC](#table_of_contents)

**************

### New_keyword 

Allocate memory on the heap.
Based on the memory you need (int, array, double ,...),it needs to find an address where I can find the memory needed. 
It's slower than using the stack, because you have more step, the computer has to find the memory.

~~~cpp
int main(){
	int a = 2;
	int* b = new int[50]; // 200 bytes of memory
	Entity* e = new Entity(); // here it called also the constructor and allocate memory on 
	// the heap for one Entity
	Entity* e = new Entity[50]; //Allocate memory on the heap for 50 object Entity
	Entity* e = new(memory_address) Entity(); //you can choose the address where it's allocate 			   // on the heap
	delete e; //neeed to release the memory on the heap by using delete
	delete[] b; //delete using [] if you define new with []
}
~~~
> new call first malloc(sizeof(int)) behind the scene ( memory allocation)


 [TOC](#table_of_contents)

************
### Implicit_conversion_Explicit_keyword 

~~~cpp
class Entity{
private:
	std::string m_Name;
	int m_Age;
public:
	Entity (const std::string& name)
		:m_Name(name), m_Age(-1){}
	 Entity(int age)
		: m_Name("Unknown"), m_Age(age){}
};
int main{
	Entity a("Louis");
	Entity b = Entity(22); 
	Entity a = "Louis"; //Implicit conversion
}
~~~

> Doesn't look very clear when you use implicit conversion, try to avoid.

~~~cpp
class Entity{
private:
	std::string m_Name;
	int m_Age;
public:
	explicit Entity (const std::string& name)
		:m_Name(name), m_Age(-1){}
	explicit Entity(int age)
		: m_Name("Unknown"), m_Age(age){}
};
int main{
	Entity a("Louis");
	Entity b = Entity(22); 
	Entity a = "Louis"; //Implicit conversion
}
~~~

We use explicit, when we want the constructor to be explicitly called. When we don't want to have the compiler doing implicit conversion we don't want. 

It's not often used, can be used in some mathematical object for example when we don't want the compiler to convert vector to number all the time.

 [TOC](#table_of_contents)


**************

### Operators_and_Operator_Overloading

Operators are just fonctions.  Helps to clean the code. 

***Operator overloading*** : give a new meaning to an operator, adding to an operator, we are allowed to change the behavior of operator. 

>operator overloading should be used as minimum as possible, and only used when It makes perfect sens, and not all the time.

*Operator Overloading example*: 
Without:
~~~cpp
struct Vector2{
	float x, y;
	Vector2(float x, float y)
		:x(x), y(y){}
	Vector2 Add(const Vector2& other) const //not going to modify the class so const, passing by reference avoid copying
	{
		return Vector2(x +other.x, y + other.y);
	}
};
int main(){
	Vector2 position (4.0f, 4.0f);
	Vector2 speed(0.5f, 1.5f);
	Vector2 result = position.Add(speed);
}
~~~
With:
~~~cpp
struct Vector2{
	float x, y;
	Vector2(float x, float y)
		:x(x), y(y){}
	Vector2 Add(const Vector2& other) const //not going to modify the class so const, //passing by reference avoid copying
	{
		return Vector2(x +other.x, y + other.y);
	}
	Vector2 operator+(const Vector2& other) const //2 way of writting 
	{
		return *this + other;
	}
	Vector2 operator+(const Vector2& other) const //Same 
	{
		return Add(other);
	}
};
int main(){
	Vector2 position (4.0f, 4.0f);
	Vector2 speed(0.5f, 1.5f);
	Vector2 result = position.Add(speed);
	Vector2 result2 = position + speed;
}
~~~

 [TOC](#table_of_contents)
 
***********

### This_keyword 

***this***:  a key word accessible throw a method (fct of a class). It's a pointer to the curent object instance that the method belongs too. 

~~~cpp
void PrintEntity(Entity* e);
class Entity{
public:
	int x,y;
	Entity(int x, int y)
	{
		Entity* e = this;
		this->x=x;
		PrintEntity(this)
	}
	int GetX() const{
		const Entity* e = this;
		return this->x
	}
};
void PrintEntity(Entity* e){
}
~~~

 [TOC](#table_of_contents)
 
********************

### Object_Lifetime

Stack is a data structure. 

We stack things on top, like a stack of books, where you need to remove the book from above to access books that are in the middle.
When you enter a scope({ }), you add a book to your stack and when you declare variable you write stuff inside your books. When you are out of the scope, it's like you are not anymore inside the book, so it's gone !

 ***On the stack, a variable will be gone when you go out of scope. ***
~~~cpp
class Entity{
public:
	Entity()
	{
		cout<<"Created"<<endl;
	}
	~Entity()
	{
		cout<<"destroyed"<<endl;
	}
};

class ScopedPtr{
private:
	Entity* m_Ptr;
public:
	ScopedPtr(Entity* ptr)
		: m_Ptr(ptr)
		{
		}
	~ScopedPtr()
	{
		delete m_Ptr;
	}
};

int main(){
	Entity e; //get destroyed at the end of scope
	Entity* e = new Entity(); //doesn't get destroyed at the end of scope
	ScopedPtr e = new Entity(); // get destroyed at the end of scope
~~~

 [TOC](#table_of_contents)

***************

### Smart_Pointers

Automate the process of allocate and delete pointers on the heap without calling new or delete. 

*unique_ptr*: ***scope pointer***, when it goes out of scope the ptr on the heap get delete. 
 > you need to #include < memory> to use smart pointers
~~~cpp
int main(){
	std::unique_ptr<Entity> entity(new Entity()); //create unique_ptr
	std::unique_ptr<Entity> entity = std::make_unique<Entity>(); //better way to create
	}
~~~
> This pointer is unique, you can not copy it for example. 

 *share_ptr*: It's usually using reference counting (count how many reference you have to your pointer, when it goes to 0 it gets deleted.

~~~cpp
int main(){
	{
		std::shared_ptr<Entity> e0; //holds reference of the shared ptr
		{
			std::shared_ptr<Entity> sharedEntity = std::make_shared<Entity>(); //created shared_ptr
			e0 = sharedEntity;
		}//doesn't die in this scope
	}//die in this scope because e0 gets delete, because no more reference !
}
~~~ 
> You can copy with shared pointers. 

*weak_ptr* : When you assign shared ptr to weak ptr it won't count has a reference, so It won't keep shared ptr alive. It won't keep shared ptr alive. 
You can ask weak_ptr: are you expired, are you still valid

~~~cpp
int main(){
	{
		std::weak_ptr<Entity> e0; //doesn't hold reference of the shared ptr, just copy
		{
			std::shared_ptr<Entity> sharedEntity = std::make_shared<Entity>(); //created shared_ptr
			e0 = sharedEntity;
		}//die in this scope, because no more reference, weak_ptr doesn't count as a reference.
	}
}
~~~ 
> Try to use smart pointers as much as possible, it's very useful and optimized. 

 [TOC](#table_of_contents)

***************

### Copying_and_Copy_Constructors

~~~cpp
struct Vector 2{
	float x,y;
};
int main(){
	Vector2 a = {2,3};
	Vector2 b = a; // a and b are 2 differents variables, we are copying.
	b.x = 2; // a will reamain the same, we are copying the value into b.
	Vector2* a = new Vector2();
	Vector2* b = a; // we are copying the ptr that have the same value.
	b++; // a will still be the same, we changed the b ptr. 
	b->x = 2; //will change a and b, because we are changing the value on the same memory address
}
~~~
>When we are assigning one variable to another (variable = variable), we are always copying except for reference. 

Deep copy, copy the entire object, for example it will also copy the content of pointers or where the pointer is pointing too.

*Copy_constructor*: used to do a deep copy of an object, used to copy object, that for example have a memory address as members and we need to have two different memory address and not the same.
~~~cpp
String(const String& other){ // to add to the object declaration;
	memcpy(this, &other, sizeof(String));
	memcpy(m_buffer, other.m_Buffer, m_Size + 1);
	}
~~~
 [TOC](#table_of_contents)

************

### Arrow_Operator 

 **->**: it's to access a member function or a member variable or reference of an object through a pointer (with a regular variable or reference you would use . )  

~~~cpp
Entity e;
e.Print();

Entity* ptr = &e;
(*ptr).print();//de-reference first then call .print()
ptr->print();//same effect as a line above but simpler and cleaner.
~~~

> It's possible to overload the array operator

*Example of overloading ->*:

~~~cpp
class Entity{
public:
	void Print() const { std::cout <<"Hello" << std::endl;}
};
class ScopedPtr{
private: 
	Entity* m_obj;
public:
	ScopedPtr(Entity* entity)//constructor
		: m_obj(entity)
		{
		}
	~ScopedPtr()//destructor
	{
		delete m_obj;
	}
	Entity* operator->(){ return m_obj;} //overload the -> operator
};
int main(){
	ScopedPtr entity = new Entity();
	entity->Print();
}
~~~
*Get the offset of value in memory*:
~~~cpp
struct Vector3{
	float x,y,z; //offset of x =0, y= 4 z= 8 in the memory (float is 4 bits)
};
int main(){
	int offset = (int)&((Vector3*)nullptr)->x;
	cout<< offset<<endl;
	}
~~~

 [TOC](#table_of_contents)
 
 **********

### Dynamic_Arrays_std_vector

It's an array list, a dynamic array. It can be resize, it doesn't have a fix size, putting element in the array will make it bigger. 

***standard_template_library***: A library field with containers, contains certain type of data, the data type that the container contains is up to you. 

> std::vector should not be called vector but array list, it has nothing to do with the mathematical array. 

*How does it work ?*
It creates a new array bigger and delete the old one every time you add an element. It's not really optimized. 
```
vector<Type> vect;
```
will allocate the  `vector`, i.e. the header info, on the stack, but the elements on the free store ("heap").
```
vector<Type> *vect = new vector<Type>;
```

allocates everything on the free store.

```
vector<Type*> vect;
```

will allocate the  `vector`  on the stack and a bunch of pointers on the free store
~~~cpp
#include <iostream>  
#include <vector>  

struct Vertex{  
    float x,y,z;  
};  
  
std::ostream& operator<<(std::ostream& stream, const Vertex& vertex){  
        stream << vertex.x << "" << vertex.y << "" << vertex.z;  
  return stream;  //overloading << to make cout work with our struct
}  
  
int main() {  
  std::vector<Vertex> example2;  
  example2.push_back({1,2,3});  
  example2.push_back({4,5,6});  
  
  std::vector<int> example;  
  example.push_back(1);  
  example.push_back(2);  
  
  for (int v : example) //here we copy, but with int we don't care 
  std::cout<<v<<std::endl;  
  std::cout<<example[0]<<std::endl;//[] is overload for std::vector
  
  for (Vertex& v : example2) //passing by reference here we don't copy a new object all the time
        std::cout<<v<<std::endl;  
  
  example.erase(example.begin() +1); //will delete the second element of the array  
  example.clear();  
  
  void Function(const std::vector<int>& example){} //pass vector by reference in fct so we don't copy, by const if we don't modify.   
}
~~~

#### Optimizing the usage of std::vector in C++
We need to continuously re-allocate memory large enough to handle new elements and copy all previous existing elements to the new location when we push_pack new element. 

How can we avoid copying our object ? 
> Knowing when copying happened is very important for optimization ! 

~~~cpp
#include <iostream>  
#include <vector>  
  
struct Vertex{  
    float x,y,z;  
  Vertex(float x, float y, float z) //default constructor  
  : x(x), y(y), z(z) {  
    }  
    Vertex(const Vertex& vertex) //copy_constructor  
  : x(vertex.x), y(vertex.y), z(vertex.z)  
    {  
        std::cout << "Copied " << std::endl;  
  }  
};  
  
std::ostream& operator<<(std::ostream& stream, const Vertex& vertex){  
        stream << vertex.x << "" << vertex.y << "" << vertex.z;  
  return stream;  
}  
  
int main() {  
    std::vector<Vertex> example2;  
  example2.reserve(3); // 2) optimization, we are telling vector we would like  
 // enough memory to store 3 objects  example2.emplace_back(1, 2, 3); // 1) optimization  
  example2.emplace_back(5, 4, 6);  
  example2.emplace_back(7, 8, 9);  
  
}  
~~~ 
*Optimization strategy*:
Using the copy_constructor we know how many times we copied our object.
1) We are constructing in the stack memory of the main function, then we copied  
main function to the actual vector class memory. We should construct this vector  
in the actual memory that the vector has allocate for us.  

2) We resized the vector twice so we copied twice more the object, if we know how  
many element we are going to push, we can optimize the initial size of vector.


[TOC](#table_of_contents)
 
 **********

### Using_Libraries
CmakeList 
***Needs to be completed !!!***

How can we use external library in our project.
Include files (header files)
Lib files
1) create Dependencies folder
2) create a folder with the name of the library
3) include & lib

***Using dynamic libraries***:


[TOC](#table_of_contents)
 
 **********

### Multiple_return_values
Usually a fonction can only return one type (if we want to return a string and an int we have a problem) and if want to return multiple variables of the same type we can use an array but it's not optimized.

*Input parameters way*:
We can pass by reference argument of the fonction and modified directly the value inside the memory address.
Example:
~~~cpp
void Function (std::string& outHello, std::string& outHello2){ //output arguments.
	outHello = "Blabla";
	outHello2 = "bibi";
}
void Function2 (std::string* outHello, std::string* outHello2){ //output arguments.
	(*outHello) = "Blabla";
	(*outHello2) = "bibi"; //with this method you can pass by argument a nullptr.
}
int main(){
	std::string hello, hello2;
	Function(&hello, nullptr);
	std::cout << hello << std::endl;
	std::cout << hello2 << std::endl;
~~~

*Using an array*
We can use an array to store multiple values and return the array.
We can also use a vector, array are created on the stack, vector will stored on line storage on the heap, so array will be faster.

*Struct way*:
~~~cpp
struct OutStrings{
	std::string Hello;
	std::string Hello2;
};
OutStrings (arguments){
	return (Hello, Hello2)
}
~~~

[TOC](#table_of_contents)
 
 **********

### Templates
You can get the compiler writing code for you based on a set of rules. 

~~~cpp
void Print (int value){
	std::cout << value << std::endl;
}
void Print (float value){
	std::cout << value << std::endl;
}
void Print (std::string value){
	std::cout << value << std::endl;
}
int main(){
	print(5);
	print(5.2f);
	print ("hello");
}
~~~
==
~~~cpp
template<typename T> // template parameters
void print (T value){ //template
	std::cout << value << std::endl;
}
int main(){
	print<int>(5);
	print(5.2f);
	print ("hello");
}
~~~
>The template doesn't exist before we called it. 
>Template specified how to create methods, fonctions, class. 

*Example for a class*:
~~~cpp
template<typename T,int N>
class Array
{
private:
	T m_array[N];
public:
	int getSize() const {return N;}
};
int main(){
	Array<int,5> array;
	std::cout << array.getSize() << std::endl;
	}
~~~

[TOC](#table_of_contents)
 
 **********
 
### Stack_vs_Heap_Memory
The stack and heap are two areas of memory we have in our ram. 
 
The performance difference is done during the allocation. Allocating on the stack is much faster, you just stack one above the other in memory, just one line a CPU instruction. Allocating on the heap is much more heavy, using new called malloc()that go throw the free list of memory, search for a block of memory of the size we need allocate it, reserved it (no one can use it after), lot of CPU instructions. Delete also is very heavy in CPU instructions. 


[TOC](#table_of_contents)
 
 **********
 
### Macros
Get evaluated during pre-processing 
~~~cpp
#define LOG(x) std::cout << x << std::endl
#if ==1
	#define 
#ifdef blabla
#elif
#else
#endif
int main(){
	LOG("Hello");
}
~~~


[TOC](#table_of_contents)
 
 **********
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE4MjY3NDM1NjMsLTE3MDQ5NDUyMDMsMT
kxNDE1OTkwNCwtNDgzNTA1MDIyLC0xMzIzMjkyMzg1LDM2NTk4
MjQxNywxNTAyNTczMTM3LC03NjU5NjUwNDMsMTU5NTczNDYzOS
wxODQ3NzM2NTIzLDE4NjY2NjMyNDYsNTEwMTQwNzkzLC0xMjU3
MTg5MzQ5LDE2ODYyNzMxMzAsLTIwMTI5MDI5MDcsLTEwNDkyNz
EzMDAsLTY4MjM0NzA3MywyMDk3Mjk5ODUsLTE5NTA1NTI1NDAs
LTEwMzU5ODI0ODBdfQ==
-->